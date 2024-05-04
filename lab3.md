# This is lab report 3 for CSE 15L

## 1 - A failure inducing input in the form of a junit test
For the report, I chose the 'ListExamples' class, which has two buggy methods. I focused on the 'merge' method, which takes two lists and adds the contents to a 
new list with the first list being added entirely and then the second list being added entirely.

Here are the two tests. The testMergeFails fails and testMergePasses passes.
' @Test
    public void testMergeFails() {
        List<String> list1 = Arrays.asList("a", "c", "e");
        List<String> list2 = Arrays.asList("b", "d", "f", "g");  
        List<String> expected = Arrays.asList("a", "b", "c", "d", "e", "f", "g");
        List<String> result = ListExamples.merge(list1, list2);
        assertEquals(expected, result);'

  '@Test
    public void testMergePasses() {
        List<String> list1 = Arrays.asList("a", "c", "e");
        List<String> list2 = Arrays.asList("b", "d"); 
        List<String> expected = Arrays.asList("a", "b", "c", "d", "e");
        List<String> result = ListExamples.merge(list1, list2);
        assertEquals(expected, result);'
    
