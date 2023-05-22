# ReverseLinkedList-

1->2->3->4->5->null ;
5->4->3->2->1->null;


--------------------------------->>> Itration approch :
206. Reverse Linked List
       class Solution {
    public ListNode reverseList(ListNode head) {
        // corner case 
        if(head==null) return null;

        // Initialisation of three pointer 
        // curr-> currElement:
        // pre ->  Initially null:
        // Nnext-> for next Node :
        ListNode curr= head;
        ListNode prev= null;
        ListNode Nnext = null;

        while(curr!=null || Nnext!=null){
               Nnext = curr.next;
               curr.next= prev;
               prev=curr;
               curr=Nnext;
            
        }
        return prev;
        


    }
}
        --------------------> BY ->RECURSION
        class Solution {
    public ListNode reverseList(ListNode head) {
        if(head==null) return head;
        
        // base case 
        if(head.next==null) return head;

        // recursive work 

        ListNode newNode = reverseList(head.next);// give reverse of head.next;

        head.next.next =head; // make null point to head :

        head.next=null;// break connection ,which is with ahead of head.

        return newNode ;// and return newnode call ;


    }
}
        
