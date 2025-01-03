### TC-> O(n)
### SC-> O(n)

### Solution
```cpp
class Node{
    public:
    int value;
    Node* next;
    Node(int val){
        value = val;
        next = NULL;
    }
};

class Solution {
public:
    int findTheWinner(int n, int k) {
        Node *head = new Node(1);

        Node *temp = head;

        for(int i=2; i <= n ; i++)
        {   
            Node* newnode = new Node(i);
            temp->next = newnode;
            temp = newnode;
        }

        temp->next = head;

        if(k > n)k = k % n ;

        Node* prev_ptr = k == 1? temp: head;
        Node* ptr = head;

        while(ptr->next != ptr)
        {
            for(int i = 0 ; i < k - 1 ; i++)
            {
                prev_ptr = ptr;
                ptr = ptr->next;
            }

            prev_ptr->next = ptr->next;
            ptr = ptr->next;
        }

        return ptr->value;
    }
};
```

###Screenshots
![Q2](https://github.com/user-attachments/assets/7dc858f3-5bab-49f7-99f1-fc378b733de5)
![2](https://github.com/user-attachments/assets/868d1532-66ad-405b-b07e-60ccf3d0569d)

