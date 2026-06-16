# Queue ( FIFO )

A linear data structure 
First In First Out
     - insertion happens at one end (**REAR**) 
     - deletion at the other end (**FRONT**). 

### Basic Operations

- **Enqueue**: Add element at rear
- **Dequeue**: Remove element from front
- **Peek/Front**: View front element without removing
- **isEmpty**: Check if queue is empty
- **isFull**: Check if queue reached max capacity (array implementation)

### How to implement ( array )

1. Initially FRONT = 0, REAR = -1
2. while Enqueue: 
    1. check if queue is full  ( REAR == size-1 ) 
    2. increment the REAR++, 
    3. add the element at REAR 
3. while Dequeue: 
    1. check is queue is empty ( FRONT > REAR )  
    2. return the element at FRONT 
    3. increment the value of FRONT++. 

> wasted space after dequeues → solved by **Circular Queue / linked list**
> 

- Code
    
    ```java
    class Queue {
        int front = 0, rear = -1;
        int arr[] = new int[100];
    		
        boolean isEmpty() { 
    		    return front > rear; 
        }
        
        boolean isFull(){
    		    return rear == arr.length -1;
    		} 
    		
        void enqueue(int x) {
            if (this.isFull()) { 
    		        System.out.println("Queue is full"); 
    		        return; 
            }
            arr[++rear] = x;
        }
        
      
        int dequeue() {
            if (this.isEmpty() { 
    				    System.out.println("Queue is empty."); 
    				    return -1; 
    		    }
            return arr[front++];
        }
        int peek() { 
    		    return this.isEmpty() ? -1 : arr[front];
        }
    }
    ```
    

### Types of Queue

1. **Simple Queue** – (array)
2. **Circular Queue** ( linked list ) 
— last position connects back to first, avoids wasted space 
3. **Priority Queue** (heap)
— elements have priority, 
— highest priority served first 
4. **Deque (Double Ended Queue)**  
— insertion/deletion possible from both ends.