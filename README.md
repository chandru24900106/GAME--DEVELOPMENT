### Name : chandru v
### Reg no : 212224230043

# EX 3 : Circle Drawing Algorithm

**AIM :**

To  implement the Bresenham’s  algorithm for circle using a c coding.


**ALGORITHM :**

Step 1 : Start.
    
Step 2 : Initialize the graphics header files and functions.
   
Step 3 : Declare the required variables and functions.
 
Step 4 : Get the co-ordinates and radius of the circle.

Step 5 : Draw the circle using the algorithm.

Step  6 : Display the output.
  
Step 7 : stop.

**Program :**
```
#include <stdio.h>
#include <conio.h>
#include <graphics.h>
#include <math.h>

void plotpoints(int xc, int yc, int x, int y) {
    putpixel(xc + x, yc + y, WHITE);
    putpixel(xc - x, yc + y, WHITE);
    putpixel(xc + x, yc - y, WHITE);
    putpixel(xc - x, yc - y, WHITE);
    putpixel(xc + y, yc + x, WHITE);
    putpixel(xc - y, yc + x, WHITE);
    putpixel(xc + y, yc - x, WHITE);
    putpixel(xc - y, yc - x, WHITE);
}

int main() {
    int gd = DETECT, gm;
    int xcenter, ycenter, radius;
    int p, x, y;

    initgraph(&gd, &gm, "C:\\Turboc3\\BGI");  // Update path based on your setup

    printf("Enter the Radius Value:\n");
    scanf("%d", &radius);
    printf("Enter the xcenter and ycenter Values:\n");
    scanf("%d %d", &xcenter, &ycenter);

    x = 0;
    y = radius;
    p = 1 - radius;

    plotpoints(xcenter, ycenter, x, y);

    while (x < y) {
        x++;
        if (p < 0) {
            p += 2 * x + 1;
        } else {
            y--;
            p += 2 * (x - y) + 1;
        }
        plotpoints(xcenter, ycenter, x, y);
    }

    getch();
    closegraph();
    return 0;
}
```
**Output :**


![Screenshot (7)](https://github.com/user-attachments/assets/919bf51e-481c-4e4b-825b-43faaa08c78a)

**Result :**

To  implement the Bresenham’s  algorithm for circle using a c coding is verified sucessfully
