# This is lab report 3 for CSE 15L

## 1 - Part 1
For the report, I chose the 'ListExamples' class, which has two buggy methods. I focused on the 'merge' method, which takes two lists and adds the contents to a 
new list with the first list being added entirely and then the second list being added entirely.

Here are the two tests. The testMergeFails fails and testMergePasses passes.
```
@Test
    public void testMergeFails() {
        List<String> list1 = Arrays.asList("a", "c", "e");
        List<String> list2 = Arrays.asList("b", "d", "f", "g");  
        List<String> expected = Arrays.asList("a", "b", "c", "d", "e", "f", "g");
        List<String> result = ListExamples.merge(list1, list2);
        assertEquals(expected, result);}
```
 ```
 @Test
    public void testMergePasses() {
        List<String> list1 = Arrays.asList("a", "c", "e");
        List<String> list2 = Arrays.asList("b", "d"); 
        List<String> expected = Arrays.asList("a", "b", "c", "d", "e");
        List<String> result = ListExamples.merge(list1, list2);
        assertEquals(expected, result);}
```
Here is the output of the two tests. There is no output on the terminal due to the bug in the method. The failure inducing input causes one of the tests to have an infinite loop, meaning I manually have to stop the tests from running.

![image](testResults.png).

Here is the buggy version of the method:
```
while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }
```

Here is the fixed version of the method:
```
while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
```


This fix addresses the issue because the value of index2 never gets incremented in the buggy version. This means that the while loop will run without stopping since the conditonal will never evaluate to true. Changing it to index2 means that the value will properly increment and the conditional can be met.
    
## Using the `grep` command

## `grep -r`

Here is the first input:
`$ grep -r "base pair" technical/plos > grep-results.txt`

Using the `wc` command:
`$ wc grep-results.txt
  3  48 412 grep-results.txt`
  
Using `-r` utilizes `grep` to count the amount of lines in `technical/plos` that contains the phrase base pair. This shows that 3 lines in `technical/plos` contain the phrase "base pair". This is important because it could help someone searching for the amount of times a certain line of code is written or how many times a method is called.

Here is the second input:
`$ grep -r "base pair" technical/biomed > grep-results.txt`

Using the `wc` command:
`$ wc grep-results.txt
  226  2326 22534 grep-results.txt`

Using `-r` utilizes `grep` to count the amount of lines in `technical/biomed` that contains the phrase base pair. This shows that 3 lines in `technical/plos` contain the phrase "base pair". This could also be useful for someone trying to find a certain date or something similar in a database.

## `grep -rHl`

Here is the first input:
`$ grep -rHl "base pair" technical/plos`

Here is the output:
`technical/plos/journal.pbio.0020190.txt
technical/plos/journal.pbio.0020223.txt`

Using `-rHl` modifier for `grep` prints out the files in the given directory containing the specified pattern. Here, it prints out the files in `technical/plos` containing the phrase "base pair". This could be very useful for someone trying to find a file regarding a particular topic if they forgot the name of it.

Here is the second input: 
`$ grep -rHl "Darwin" technical/`

Here is the second output:

`technical/biomed/1471-2105-3-2.txt
technical/plos/journal.pbio.0020046.txt
technical/plos/journal.pbio.0020071.txt
technical/plos/journal.pbio.0020302.txt
technical/plos/journal.pbio.0020311.txt
technical/plos/journal.pbio.0020346.txt
technical/plos/journal.pbio.0020347.txt
technical/plos/journal.pbio.0020439.txt`

This command is printing every file in `technical` that contains the phrase "Darwin". This could be useful for someone who needs to find all files mentioning a particular article or cited author in order to properly cite their work.

## `grep --color`

Here is the first input:
`$ grep --color "Darwin" technical/plos/journal.pbio.0020046.txt`

Here is the first output:
`answers to possible questions and criticisms to avoid stuttering. Charles |Darwin| also
stuttered; interestingly, his grandfather Erasmus |Darwin| suffered from the same condition,`

Since markdown does not support color (I think, I looked and that was the general consensus), I put the words in bars. The words in bars (Darwin) are printed in red in my vsCode output. This command prints the sought after pattern in color (red by default) and some of the text near it. This could be useful for someone trying to find the context in which a term was used.

Here is the second input:
`$ grep --color "deleterious" technical/plos/journal.pbio.0020019.txt`

Here is the second output:
`new mutations (which may be |deleterious|), potentially allowing individuals to store this`

I did this because I thought that was a cool word. The `grep --color` command is outputting a short segment of text where the word "deleterious" is highlighted in red. This could be useful for someone trying to understand the definition of a word.

## `grep -rL`

Here is the first input:
`$ grep --line-number "deleterious" technical/plos/journal.pbio.0020019.txt`
Here is the first output:
`14:        new mutations (which may be deleterious), potentially allowing individuals to store this`

`grep --line-number` is printing out the line number(s) of the sought after pattern in the given files. In this case, it is printing out the line number of the word "deletrious" in the file `journal.pbio.0020019.txt`. This could be useful for someone trying to find the specific line that a method or function appears.

Here is the second input: 
`$ grep --line-number "questionnaires" technical/government/Alcohol_Problems/Session2-PDF.txt`

Here is the second output:
`13:further examine and refine alcohol-screening questionnaires in the
132:one or a combination of structured questionnaires.10 Screening
134:accurate or as sensitive as structured questionnaires for
150:26% of patients who screened negative on structured questionnaires.
156:Structured questionnaires
164:questionnaires.7
214:In addition to these questionnaires, NIAAA suggests that all
291:questionnaires
301:NET. Further sequencing of questions within questionnaires may also
371:staff does not use structured questionnaires for alcohol screening.
389:effective. Self-administered questionnaires, computer screen
392:health questionnaires or existing registration, physician, and
419:performance of structured questionnaires and try computer-based
550:screening questionnaires in women. JAMA 1998;280:166-71.`

Here, the `grep --line-number` command is printing all line numbers containing the phrase "questionnaires" in the file `Session2-PDF.txt`. This could be useful for someone trying to ensure that a document is following a certain formatting specification where a certain element must be in a certain place.

All information regarding the `grep` commands came from the gnu website.

`“Grep .” GNU Grep 3.11, www.gnu.org/software/grep/manual/grep.html. Accessed 4 May 2024. `
