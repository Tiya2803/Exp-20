# Experiment 20

# Aim:
To study and implement Sorting Algorithm.

# Theory:
Sorting is a way to arrange elements in a particular order. We will be understand 3 types of sorting which are:

→ Selection Sort

→ Insertion Sort

→ Bubble Sort


Selection Sort: A simple comparison-based sorting algorithm. It sorts an array by repeatedly finding the minimum element from the unsorted portion of the array and placing it at the beginning.
Selection Sort Steps:

Find the smallest element in the unsorted array.
Swap it with the first element of the unsorted array.
Move the boundary between the sorted and unsorted parts by one element.
Repeat the process until the array is sorted.

Insertion Sort: This works by repeatedly taking an element from the unsorted portion and inserting it into its correct position within the sorted portion of the array.
Insertion Sort Steps:

Assume the first element is sorted.
Take the next element and compare it with the elements in the sorted portion.
Shift all larger elements in the sorted part to the right.
Insert the current element in its correct position.
Repeat the process for all elements.

Bubble Sort: A simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The process is repeated until the list is sorted.
Bubble Sort Steps:

Compare adjacent elements.
Swap if necessary.
Check if a swap was made in the current pass.
If no swaps were made, exit early.


# Code:

a.

#include <iostream>
using namespace std;

void swap(int *a, int *b) 
{
  int temp = *a;
  *a = *b;
  *b = temp;
}


void display(int ar[], int len) 
{
  for (int i = 0; i < len; i++) 
  {
    cout << ar[i] << " ";
  }
  cout << endl;
}

void selectsort(int ar[], int len) 
{
  for (int j = 0; j < len - 1; j++) 
  {
    int mi = j;
    for (int i = j + 1; i < len; i++) 
    {
      if (ar[i] < ar[mi])
        mi = i;
    }

    swap(&ar[mi], &ar[j]);
  }
}

int main() 
{
  int data[] = {50, 25, 10, 15, 30};
  int len = sizeof(data) / sizeof(data[0]);
  cout << "Original Array:";
  display(data, len);
  selectsort(data, len);
  cout << "Selection sorted array:";
  display(data, len);
}


b.

#include <iostream>
using namespace std;

void insertsort(int ar[], int n) 
{
    for (int i = 1; i < n; i++) 
    {
        int key = ar[i];
        int j = i - 1;

        while (j >= 0 && ar[j] > key) 
        {
            ar[j + 1] = ar[j];
            j = j - 1;
        }
        ar[j + 1] = key;
    }
}

void display(int ar[], int n) 
{
    for (int i = 0; i < n; i++) 
    {
        cout << ar[i] << " ";
    }
    cout << endl;
}

int main() {
    int ar[] = {12, 16, 2, 8, 6};
    int n = sizeof(ar) / sizeof(ar[0]);

    cout << "Original array: ";
    display(ar, n);
    insertsort(ar, n);
    cout << "Insertion Sorted array: ";
    display(ar, n);

    return 0;
}


c.

#include <iostream>
using namespace std;

void bubbleSort(int ar[], int len) 
{

  for (int j = 0; j < len -1; ++j) 
  {
      
    for (int i = 0; i < len - j - 1; ++i) 
    {

      if (ar[i] > ar[i + 1]) 
      {
        int temp = ar[i];
        ar[i] = ar[i + 1];
        ar[i + 1] = temp;
      }
    }
  }
}

void display(int ar[], int len) 
{
  for (int i = 0; i < len; ++i) 
  {
    cout << "  " << ar[i];
  }
  cout << "\n";
}

int main() 
{
  int data[] = {-11, 3, 0, 11, -1};
  int len = sizeof(data) / sizeof(data[0]);
  cout << "Original array: ";
  display(data, len);
  bubbleSort(data, len);
  cout << "Bubble Sorted array: ";  
  display(data, len);
}

# Conclusion:

→ We learnt about sorting in C++.

→ We learnt the use case of the types of sorting in C++.

