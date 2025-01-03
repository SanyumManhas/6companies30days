### TC-> O((x2-x1)*(y2-y1))
### SC-> O(1)

### Solution

```cpp
class Solution {
public:
    bool checkCircle(int r, int xc, int yc, int x, int y)
    {
        int lhs = ((x-xc)*(x-xc)) + ((y-yc)*(y-yc));
        int rhs = r*r;
        return lhs <= rhs;
    }
    bool checkOverlap(int radius, int xCenter, int yCenter, int x1, int y1, int x2, int y2) {

        for(int i = x1; i <= x2 ; i++)
        {
            for(int j= y1; j<= y2; j++)
            {
                if(checkCircle(radius, xCenter, yCenter, i, j))
                {
                    return true;
                }
            }
        }
        return false;
    }
};
```

###Screenshots
![Q1](https://github.com/user-attachments/assets/019c67c9-5cdc-4275-8179-00770e345f8c)
![1](https://github.com/user-attachments/assets/79e72c1e-f6e8-4b3a-b94b-858b59261b37)



