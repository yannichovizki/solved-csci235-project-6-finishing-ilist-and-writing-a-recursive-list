Download Link: https://assignmentchef.com/product/solved-csci235-project-6-finishing-ilist-and-writing-a-recursive-list
<br>
<strong>Task #1: Finishing </strong><strong>IList</strong>

<ul>

 <li>Update the IList class so that it implements the interface, List235.</li>

 <li>Fill in the methods that are not yet implemented. You can copy the code from the previous lab to the IList Test every method.</li>

</ul>

<strong>Task #2: Writing a recursive list</strong>

<ul>

 <li>Complete the remaining methods in RList and the corresponding recursive RNode

  <ul>

   <li>Notice how the methods in the node class that modify the list return <strong>a node representing</strong> <strong>the <em>rest</em> of the modified list</strong>.</li>

   <li>A node keeps itself in the list <u>by modifying its </u><u>next</u><u> link and returning </u><u>this</u>.</li>

   <li>A node removes itself from the list <u>by returning a different node</u>.</li>

  </ul></li>

 <li>Test every method.</li>

</ul>







Example:

<strong>public class RList implements List235</strong> {




private RNode head;




public RList() {

head = null;

}




<strong>public void printList()</strong> {

System.out.print(“[ “);

if (head != null) {

head.print();

}

System.out.println(” ]”);

}







/**

* Get the value of the item at a specified position.

* @param position The position in the list.

* @return The value at position in the list.

* PRECONDITION: position &gt;= 0 and position &lt; length of this list

*/

<strong>public int elementAt(int position)</strong> {

if (head != null) return head.elementAt(position);

throw new RuntimeException(“The list is empty”);

}




/**

* Delete the first occurrence of item in this list, if any.

* @param item The item to delete

*/

<strong>public void deleteFirstOccurrence(int item)</strong> {

if (head != null) {

head = head.deleteFirstOccurrence(item);

}

}

…




In RNode:




<strong>public class RNode</strong> {




private final int datum;




private RNode next;




public RNode(int datum, RNode next) {

this.datum = datum;

this.next = next;

}




public int datum() { return datum; }

public RNode next() { return next; }




public void print() {

System.out.print(datum+” “);

if (next != null) {

next.print();

}

}




public int elementAt(int position) {

if (position == 0) return datum;

else return next.elementAt(position-1);

}




public RNode deleteFirstOccurrence(int item) {




// Prep #18 for Apr. 13













<strong>CSCI 235 Spring 2020</strong>




<strong>Project #6 (Due: 5 pm on Tuesday, Apr. 21)                                                                                     </strong>

<strong>Part B:                                    </strong>

<strong>                                                                                                                        </strong>

<strong> </strong>

<strong>Documentation and style will be assessed as part of your grade</strong>. <strong>Follow the full code guidelines.</strong>




Download four more Java files from the course site: DList, DLNode, List235Maker, and ListTest.




<strong>Doubly-linked List</strong>




Each node in a doubly-linked list has two links, one for forward (next) and the other for backward (previous). The classes DList and DLNode provide a framework for implementing a doubly-linked list, based on the iterative version.




The DLNode class has methods for splicing a node into or out of a list. You need to fill in the body of spliceAfter.




Write the bodies of DList methods according to the instructions. You need to provide findLast(), which will make insertAtBack() work. The other missing methods can be copied from your IList with some changes.




Use printListReverse() to see if your methods in DLNode and DList properly work. The method prints the list in reverse order by following its previous links.







<strong>Testing the lists:</strong>

You need two files: List235Maker and ListTest. Your lists will be evaluated by this program.

The ListTest class provides a main method that you can use to test the different versions of List235 interface. Use the following commands to test your lists:

$ java ListTest IList      (for testing IList)

$ java ListTest RList      (for testing RList)







You can add other tests to the testing driver if necessary.


