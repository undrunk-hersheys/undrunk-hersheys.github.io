---
layout: post
title:  "matlab_onramp"
date:   2025-03-04 19:05:00 +0900
categories: matlab
---


## MATLAB Onramp Summary

### **Basic Syntax**
| Example | Description |
|---------|------------|
|  x = pi  | Use the equal sign ( = ) to create a variable. The left-hand side ( x ) stores the value on the right-hand side ( pi ). |
|  y = sin(-5)  | Use parentheses to pass input values to a function. |

### **Desktop Management**
| Function | Example | Description |
|----------|--------|------------|
|  save  |  save data.mat  | Saves the current workspace to a MAT file. |
|  load  |  load data.mat  | Loads variables from a MAT file into the workspace. |
|  clear  |  clear  | Clears all variables from the workspace. |
|  clc  |  clc  | Clears all text from the Command Window. |
|  format  |  format long  | Changes the way numerical output is displayed. |

### **Array Types**
| Example | Description |
|---------|------------|
|  4  | Scalar |
|  [3 5]  | Row vector |
|  [1;3]  | Column vector |
|  [3 4 5;6 7 8]  | Matrix |

### **Vectors with Uniform Spacing**
| Example | Description |
|---------|------------|
|  1:4  | Creates a vector from 1 to 4 with a step of 1 using the colon ( : ) operator. |
|  1:0.5:5  | Creates a vector from 1 to 5 with a step of 0.5. |
|  linspace(1,10,5)  | Creates a vector with 5 elements, evenly spaced between 1 and 10. |

### **Creating Matrices**
| Example | Description |
|---------|------------|
|  rand(2)  | Creates a **2×2** square matrix with random values. |
|  zeros(2,3)  | Creates a **2×3** rectangular matrix filled with zeros. |

### **Indexing**
| Example | Description |
|---------|------------|
|  A(end,2)  | Accesses the element in the last row and second column. |
|  A(2,:)  | Accesses the entire second row. |
|  A(1:3,:)  | Accesses all columns of the first three rows. |
|  A(2) = 11  | Changes the value of the second element in the array to 11. |

### **Array Operations**
| Example | Result | Description |
|---------|--------|------------|
|  [1 1; 1 1] * [2 2; 2 2]  |  4 4  <br>  4 4  | Performs **matrix multiplication**. |
|  [1 1; 1 1] .* [2 2; 2 2]  |  2 2  <br>  2 2  | Performs **element-wise multiplication**. |

### **Multiple Outputs**
| Example | Description |
|---------|------------|
|  [xrow, xcol] = size(x)  | Stores the number of rows and columns of  x  in two different variables. |
|  [xMax, idx] = max(x)  | Computes the maximum value of  x  and its index. |

### **Help Documentation**
| Example | Description |
|---------|------------|
|  doc randi  | Opens the help documentation page for the  randi  function. |

### **Plotting**
| Example | Description |
|---------|------------|
|  plot(x, y, "ro-","LineWidth",5)  | Plots a red ( r ) dashed ( - ) line with circle ( o ) markers and a thick line width. |
|  hold on  | Adds the next line to the existing plot. |
|  hold off  | Creates a new axis for the next plot. |
|  title("My Title")  | Adds a title to the plot. |

### **Working with Tables**
| Example | Description |
|---------|------------|
|  data.HeightYards  | Extracts the variable  HeightYards  from the table  data . |
|  data.HeightMeters = data.HeightYards * 0.9144  | Derives a new table variable from existing data. |

### **Logical Operations**
| Example | Description |
|---------|------------|
|  [5 10 15] > 12  | Compares the vector elements with 12. |
|  v1(v1 > 6)  | Extracts all elements in  v1  that are greater than 6. |
|  x(x==999) = 1  | Replaces all values equal to  999  in  x  with  1 . |

### **Programming**
| Example | Description |
|---------|------------|
|  if x > 0.5  <br>  y = 3  <br>  else  <br>  y = 4  <br>  end  | If  x  is greater than  0.5 ,  y  is set to  3 . Otherwise,  y  is set to  4 . |
|  for c = 1:3  <br>  disp(c)  <br>  end  | The loop counter ( c ) iterates through the values  1:3  (1, 2, and 3). <br> The loop body displays each value of  c . |

