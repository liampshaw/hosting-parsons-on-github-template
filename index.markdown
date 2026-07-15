---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Computation for Bioscientists - coding problems
---
# About this page

For each problem, your task is to shuffle around the lines of code into the correct solution. Some of the problems also include lines of code that are **incorrect** and shouldn't be included in your solution. Good luck!

## Hello World!
Re-arrange the blocks below so they print out "Hello World!". 

<div id="p1-sortableTrash" class="sortable-code"></div>
<div id="p1-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p1-feedbackLink" value="Get Feedback" type="button" />
    <input id="p1-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function() {
  var initial = "print(\"Hello\")\n" +
    "print(\" \")\n" +
    "print(\"World\")\n" +
    "print(\"!\")";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p1-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p1-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>


## Counting k-mers
A k-mer is a subsequence of length k. Construct a Python function that will count all the k-mers in a larger sequence and return the result as a dictionary.

<div id="pKmers-sortableTrash" class="sortable-code"></div> 
<div id="pKmers-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="1532-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="1532-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "def count_kmers(seq, k):\n" +
    "    &quot;&quot;&quot;Count overlapping k-mers in seq. Returns a dict {kmer: count}.&quot;&quot;&quot;\n" +
    "    counts = {}\n" +
    "    for i in range(len(seq) - k + 1):\n" +
    "        kmer = seq[i:i+k]\n" +
    "        counts[kmer] = counts.get(kmer, 0) + 1\n" +
    "    return counts\n" +
    "for i in range(len(seq)):       #distractor\n" +
    "kmer = seq[i:i+k+1]#distractor\n" +
    "counts[kmer] = counts[kmer] + 1#distractor\n" +
    "return kmer#distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "1532-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "python3": true,
    "trashId": "1532-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#1532-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#1532-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>


## Parsons 5 (Turtle Grader)
Construct a program by dragging&amp;dropping and reordering lines. The constructed program should draw a triangle like shown below.

<div id="p5-sortableTrash" class="sortable-code"></div>
<div id="p5-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p5-feedbackLink" value="Get Feedback" type="button" />
    <input id="p5-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = "REPEAT 3 TIMES\n" +
    "  forward(100)\n" +
    "  left(120)\n" +
    "ENDREPEAT";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p5-sortable",
    "max_wrong_lines": 1,
    "grader": ParsonsWidget._graders.TurtleGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p5-sortableTrash",
    "executable_code": "for i in range(0,3):\nmyTurtle.forward(100)\nmyTurtle.left(120)\npass",
    "programmingLang": "pseudo",
    "turtleModelCode": "modelTurtle.forward(100)\nmodelTurtle.left(120)\nmodelTurtle.forward(100)\nmodelTurtle.left(120)\nmodelTurtle.forward(100)\nmodelTurtle.left(120)",
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p5-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p5-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>

### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)
