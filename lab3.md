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
    
## Using the grep command

# grep -r

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
