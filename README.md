# Data-Structure-and-Algorithm-in-Python
Data Structure and Algorithm in Python

Data Structure and Algorithm in Python
# Example of Big o. We pass the value n that show the worst case time complecxity O(n)
def item_no(n):
    for i in range(n):
        print(i)
item_no(10)

# Drop Constant
def item_a(n):
    for i in range(n): # this print the number and show the time complexity is n but j is also the complexity n that is:
        print(i)       #  n + n = 2n In this case we drop the constant and the complexity is  O(n).
        
        
    for j in range(n):
        print(j)
item_a(10)

# time complexity of O(n*n)
def item_b(n):
    for i in range(n): # when the loop inside the loop the time complexity is n square if you add more loop then the complexity is n cube
        for j in range(n): # n*n That print the item 0 to 99
            print(i,j)
item_b(10)


# Drop Non-Dominents value time complexity O(n*n)
def item_c(n):
    for i in range(n):
        for j in range(n): # nested for loop 
            print(i,j)
            
    for k in range(n): # other one for loop
        print(k)
item_c(10) # the total time complexity is O(n*n + n) so we drop the non-dominents value. SO the time complexity is O(n*n)

# Time Complexity of O(1)
def item_d(n):
    return n+n # this is performing the addition operator that give the time complexity 1 so the time complexity is O(1)
item_d(10)   

# time complexity of nLogn: The is the most efficient way to finding the number. Firstly it devide the array into two parts
0
1
2
3
4
5
6
7
8
9
0
1
2
3
4
5
6
7
8
9
0
1
2
3
4
5
6
7
8
9
0 0
0 1
0 2
0 3
0 4
0 5
0 6
0 7
0 8
0 9
1 0
1 1
1 2
1 3
1 4
1 5
1 6
1 7
1 8
1 9
2 0
2 1
2 2
2 3
2 4
2 5
2 6
2 7
2 8
2 9
3 0
3 1
3 2
3 3
3 4
3 5
3 6
3 7
3 8
3 9
4 0
4 1
4 2
4 3
4 4
4 5
4 6
4 7
4 8
4 9
5 0
5 1
5 2
5 3
5 4
5 5
5 6
5 7
5 8
5 9
6 0
6 1
6 2
6 3
6 4
6 5
6 6
6 7
6 8
6 9
7 0
7 1
7 2
7 3
7 4
7 5
7 6
7 7
7 8
7 9
8 0
8 1
8 2
8 3
8 4
8 5
8 6
8 7
8 8
8 9
9 0
9 1
9 2
9 3
9 4
9 5
9 6
9 7
9 8
9 9
0 0
0 1
0 2
0 3
0 4
0 5
0 6
0 7
0 8
0 9
1 0
1 1
1 2
1 3
1 4
1 5
1 6
1 7
1 8
1 9
2 0
2 1
2 2
2 3
2 4
2 5
2 6
2 7
2 8
2 9
3 0
3 1
3 2
3 3
3 4
3 5
3 6
3 7
3 8
3 9
4 0
4 1
4 2
4 3
4 4
4 5
4 6
4 7
4 8
4 9
5 0
5 1
5 2
5 3
5 4
5 5
5 6
5 7
5 8
5 9
6 0
6 1
6 2
6 3
6 4
6 5
6 6
6 7
6 8
6 9
7 0
7 1
7 2
7 3
7 4
7 5
7 6
7 7
7 8
7 9
8 0
8 1
8 2
8 3
8 4
8 5
8 6
8 7
8 8
8 9
9 0
9 1
9 2
9 3
9 4
9 5
9 6
9 7
9 8
9 9
0
1
2
3
4
5
6
7
8
9
20
Classes and Objects
# class is very import in every data structure. 
class cookie:
    def __init__(self, color): #_init_ is use to intialize value color is parameter
        self.color = color   # seld is used to access methods and attributes
    def get_color(self):
        return self.color
    def set_color(self, color):
        self.color = color
        
new_cookie = cookie("Blue")
new_cookie1 = cookie("white")
print("The cookie colo is", new_cookie.get_color())
print("The cookie colo is", new_cookie1.get_color())
    
    
#pinter

#pointer is very useful in data structure and algorithm 

num1 = 10
num2 = num1
print("Value before updation")
print(num1)
print(num2)
num2 = 20 # this value change the num2 value
print("value after updation")
print(num1)
print(num2)

# another example of pointer 
dict1 = {"value": 12}
dict2 = dict1
print("Dict 1 is: ", dict1)
print("Dict 2 is: ", dict2)

dict1['values'] = 22
print("updated value of dict1 is:  ", dict1)
print("updated value of dict2 is:  ", dict2)
The cookie colo is Blue
The cookie colo is white
Value before updation
10
10
value after updation
10
20
Dict 1 is:  {'value': 12}
Dict 2 is:  {'value': 12}
updated value of dict1 is:   {'value': 12, 'values': 22}
updated value of dict2 is:   {'value': 12, 'values': 22}
Linked list
Linked list does not have index. Linked list has conteious memory. In linked list the first item is head and last item is node.

# constructor in linked list
class Node:
    def __init__(self,value): # create a new value 
        self.value = value
        self.next = None
        
class LinkedList:
    def __init__(self,value):
        new_node = Node(value)
        self.head = new_node
        self.tail = new_node
        self.length = 1

        
    def print_List(self):
        temp = self.head
        while temp is not None:
            print(temp.value)
            temp = temp.next

    def append(self,value): # this method is use to create a new node at the end
        new_node = Node(value)
        if self.length == 0:
            self.head = new_node
            self.tail = new_node
        else:
            self.tail.next = new_node
            self.tail = new_node
        self.length +=1
        return True  #this method is also return True or False
    
    
    def pop(self):
        if self.length ==0:
            return None
        temp = self.head
        pre = self.head
        while(temp.next):
            pre = temp
            temp = temp.next
        self.tail = pre
        self.tail.next = None
        self.length -=1
        if self.length ==0:
            self.head = None
            self.tail = None
        return temp
    
    def prepend(self,value): # prepend is used to add the method at the first 
        new_node = Node(value)
        if self.length==0:
            self.head = new_node
            self.tail = new_node
        else:
            new_node.next = self.head
            self.head = new_node
        self.length+=1
        return True
    
    # pop first 
    def pop_first(self):
        if self.length==0:
            return None
        temp = self.head
        self.head = self.head.next 
        temp.next = None
        self.length -=1
        if self.length ==0:
            self.tail = None
        return temp
    
    
    # GET method 
    def get(self,index):
        if index<0 or index >= self.length:
            return None
        temp = self.head
        for _ in range(index):
            temp = temp.next
        return temp.value
    
    def reverse(self):
        temp = self.head
        self.head = self.tail
        self.tail = temp
        after = temp.next
        before = None
        for _ in range(self.length):
            after = temp.next
            temp.next = before
            before = temp 
            temp = after
    

    
my_Linked_List = LinkedList(5)
my_Linked_List.append(1)
my_Linked_List.append(6)
my_Linked_List.append(7)
my_Linked_List.pop() # remove 1 item if i write again then give the empty list
my_Linked_List.prepend(3) # 3 is added at the first of the array
my_Linked_List.get(1)
my_Linked_List.pop_first() # removing the first element
my_Linked_List.reverse()

my_Linked_List.print_List()
6
1
5
 # insert method
    def insert(self,index,value):
        if index<0 or index>self.length:
            return False
        if index == 0:
            return self.prepend(value)
        if index == self.length:
            return self.append(value)
        new_node = Node(value)
        temp = self.get(index-1)
        new_node.next = temp.next
        temp.next = new_node
        self.length +=1
        return True
    
    # remove method
    def remove(Self,index):
        if index <0 or index>=self.length:
            return None
        if index==0:
            return self.pop_first()
        if index == self.length-1:
            return self.pop()
        pre = self.get(index-1)
        temp = pre.next
        pre.next = temp.next
        temp.next = None
        self.length -=1
        return temp

my_Linked_List.insert(1,1)
my_Linked_List.remove(1)
  Input In [15]
    def insert(self,index,value):
    ^
IndentationError: unexpected indent
Doubly Linked List
class Node:
    def __init__(self,value):
        self.value = value
        self.next = None
        self.prev = None
    
class DoublyLinkedList:
    def __init__(self,value):
        new_node = Node(value)
        self.head = new_node
        self.tail = new_node
        self.length = 1
    
    def print_List(self):
        temp = self.head
        while temp is not None:
            print(temp.value)
            temp = temp.next
            
    def append(self,value):
        new_Node = Node(value)
        if self.head is None:
            self.head = new_node
            self.tail = new_node
        else:
            self.tail.next = new_Node
            new_Node.prev = self.tail
            self.tail =  new_Node
        self.length +=1
        return True
            
    def pop(self):
        if self.length ==0:
            return None
        temp = self.tail
        if self.length == 0:
            self.head =None
            self.tail = None
        else:
            self.tail = self.tail.prev
            self.tail.next = None
            temp.prev = None
        self.length -=1
        
    
    def prepend(self,value):
        new_Node = Node(value)
        if self.length == 0:
            self.head = new_Node
            self.tail = new_Node
        else:
            new_Node.next = self.head
            self.head.prev = new_Node
            self.head = new_Node
        self.length+=1
        
        
    def pop_first(self):
        if self.length ==0:
            return None
        temp = self.head
        if self.length==1:
            self.head = None
            self.tail = None
        else:
            self.head = self.head.next
            self.head.prev = None
            temp.next = None
        self.length -=1
        return temp
    
    def get(self,index):
        if index<0 or index>=self.length:
            return None
        temp = self.head
        if index<self.length/2:
            for _ in range(index):
                temp = temp.next
        else:
            temp = self.tail
            for _ in range(self.length - 1, index, -1):
                temp = temp.prev
        return temp.value
    
    
    def set_value(self,index,value):
        temp = self.get(index)
        if temp:
            temp.value = value
            return True
        return False
    
    def insert(self, index, value):
        if index<0 or index>self.length:
            return False
        if index == 0:
            return self.prepend(value)
        if index == self.length:
            return self.append(value)
        
        new_Node = Node(value)
        before = self.get(index-1)
        after = before.next
        
        
        new_node.prev = before
        new_node.next = after
        before.next = new_node
        after.prev  = new_node
        
        self.length +=1
        return True
    
    def remove(self,index):
        if index<0 or index<=self.length:
            return None
        if index ==0:
            return self.pop_first()
        if index==self.length - 1:
            return self.pop()
        temp = self.get(index)
        temp.next.prev = temp.prev
        temp.prev.next = temp.next
        temp.next = None
        temp.prev = None
        
        self.length -=1
        return temp
    
    
my_doubly_Linked_List = DoublyLinkedList(5)
my_doubly_Linked_List.append(4)
my_doubly_Linked_List.append(8)
my_doubly_Linked_List.pop()
my_doubly_Linked_List.prepend(12)
my_doubly_Linked_List.pop_first()

print(my_doubly_Linked_List.get(0))
# print(my_doubly_Linked_List.set_value(1,10))
# my_doubly_Linked_List.insert(1,2)
#my_doubly_Linked_List.remove(2),"\n")
my_doubly_Linked_List.print_List()
5
5
4
Stack & Queue
class Node:
    def __init__(self,value):
        self.value = value
        self.next = None

        
class Stack:   #Create stack Stack is working as LIFO
    def __init__(self,value):
        new_node = Node(value)
        self.top = new_node
        self.height = 1
    
    def print_Stack(self):
        temp = self.top
        while temp is not None:
            print(temp.value)
            temp = temp.next
        
        
        
    def push(self,value): # Adding the method 
        new_node = Node(value)
        if self.height==0:
            self.top = new_node
        else:
            new_node.next = self.top
            self.top = new_node
        self.height+=1
        
    def pop(self):
        if self.height==0:
            return None
        temp = self.top
        self.top = self.top.next
        temp.next = None
        self.height-=1
    
            
        
my_stack = Stack(4)
my_stack.push(1)
my_stack.push(3)
my_stack.pop()
my_stack.print_Stack()
1
4
Queue
is working as FIFO

class Node:
    def __init__(self,value):
        self.value = value
        self.next = None
    
class Queue:
    def __init__(self,value):
        new_node = Node(value)
        self.first = new_node
        self.last = new_node
        self.length = 1
         
    def print_queue(self):
        temp = self.first
        while temp is not None:
            print(temp.value)
            temp = temp.next
            
    def enqueue(self,value):
        new_node = Node(value)
        if self.first is None:
            self.first = new_node
            self.last = new_node
        else:
            self.last.next = new_node
            self.last = new_node
            
        self.length +=1
    
    def dequeue(self):
        if self.length == 0:
            return None
        temp = self.first
        if self.length==1:
            self.first = None
            self.last = None
        else:
            self.first = self.first.next
            temp.next = None
        self.length-=1
        return temp
            
my_queue = Queue(3)
my_queue.enqueue(4)
my_queue.enqueue(5)
my_queue.enqueue(6)
my_queue.dequeue()
my_queue.print_queue()
5
6
Trees
# Bunary Tree Constructor
class Node:
    def __init__(self,value):
        self.value = value
        self.left = None
        self.right = None

class BinarySearchTree:
    def __init__(self):
        self.root = None
        
    def insert(self,value):
        new_root = Node(value)
        if self.root == None:
            self.root = new_root
            return True
        temp = self.root
        while(True):
            if new_root.value == temp.value:
                return False
            if new_root.value<temp.value:
                if temp.left is None:
                    temp.left = new_root
                    return True
                temp = temp.left
            else:
                if temp.right is None:
                    temp.right = new_root
                    return True
                temp = temp.right
                
        
my_tree = BinarySearchTree()
my_tree.insert(2)
my_tree.insert(1)
my_tree.insert(3)

print(my_tree.root)
print(my_tree.root.value)
print(my_tree.root.left.value)
print(my_tree.root.right.value)

        
<__main__.Node object at 0x0000020D0F1E7C70>
2
1
3
Hash Table
hash table example is Dictionay. Dictionary is working as hash table.

# The technique of dealing with collisions where you jut put them at the same address is called separate chaining.
# Popular way of dealing with cillisions, if we already have a key value pair at the address 
# if the collision value of which have different kay value that shift into next next address is called linear Probing (open adressing).
# the another method of collison is that we create a list and stores address.
class HashTable:
    def __init__(self,size=7):
        self.data_map = [None]*size
    
    def _hash(self,key):
        my_hash = 0
        for letter in key:
            my_hash = (my_hash + ord(letter)*23) % len(self.data_map) # ord is the short of ASCII
        return my_hash

    def print_table(self):
        for i,val in enumerate(self.data_map):
            print(i,":",val)
    def set_item(self, key, value):
        index = self._hash(key)
        if self.data_map[index] == None:
            self.data_map[index] = []
        self.data_map[index].append([key,value])
        
    def get_item(self,key):
        index = self._hash(key)
        if self.data_map[index] is not None:
            for i in range(len(self.data_map[index])):
                if self.data_map[index][i][0] == key:
                    return self.data_map[index][i][1]
        return None
    
    def keys(self):
        all_keys = []
        for i in range(len(self.data_map)):
            if self.data_map is not None:
                for j in range(len(self.data_map[i])):
                    all_keys.append(self.data_map[i][j][0])
        return all_keys
    

my_hash_table = HashTable()
my_hash_table.set_item("Bottle", 2000)
my_hash_table.set_item("Coke", 500)
my_hash_table.set_item("sprite", 1000)
print(my_hash_table.get_item('Bottle'))
print(my_hash_table.get_item('Coke'))
print(my_hash_table.get_item('red bul'))

print(my_hash_table.keys)

my_hash_table.print_table()
        
    
2000
500
None
>
0 : None
1 : None
2 : [['Coke', 500]]
3 : [['sprite', 1000]]
4 : [['Bottle', 2000]]
5 : None
6 : None
Graph
class Graph:
    def __init__(self):
        self.adj_List = {}
        
    def print_graph(self):
        for vertex in self.adj_List:
            print(vertex, ':', self.adj_List[vertex])
            
    def add_vertex(self, vertex):
        if vertex not in self.adj_List.keys():
            self.adj_List[vertex] = []
            return True
        return False
    def add_edge(self,v1,v2):
        if v1 in self.adj_List.keys() and v2 in self.adj_List.keys():
            self.adj_List[v1].append(v2)
            self.adj_List[v2].append(v1)
            return True
        return False
    
    def remove_edge(self,v1,v2):
        if v1 in self.adj_List.keys() and v2 in self.adj_List.keys():
            self.adj_List[v1].remove(v2)
            self.adj_List[v2].remove(v1)
            return True
        return False
    
    
    def remove_vertex(self,vertex):
        if vertex in self.adj_List.keys():
            for other_vertex in self.adj_List[vertex]:
                self.adj_List[other_vertex].remove(vertex)
            del self.adj_List[vertex]
            return True
        return False
    
my_graph = Graph()
my_graph.add_vertex("A")
my_graph.add_vertex("B")
my_graph.add_vertex("C")
my_graph.add_edge('A','B')
my_graph.add_edge('B','C')
my_graph.add_edge('C', 'A')
my_graph.remove_edge('C','A')
my_graph.remove_vertex("A")
my_graph.print_graph()
B : ['C']
C : ['B']
Recursion
The function that calls itself

def functionThree():
    print("Three")

def functionTwo():
    functionThree()
    print("Two")

def functionOne():
    functionOne()
    print("One")
    
functionOne()
    
def factorial(n):
    if n==1:
        return 1
    return n*factorial(n-1)

factorial(4)
24
Basic Sorts
# Bubble Sort
def bubble_sort(my_List):
    for i in range(len(my_List)-1,0,-1):
        for j in range(i):
            if my_List[j]>my_List[j+1]:
                temp = my_List[j]
                my_List[j] = my_List[j+1]
                my_List[j+1] = temp
    return my_List

print(bubble_sort([6,1,3,7,3,5,2,4]))
[1, 2, 3, 3, 4, 5, 6, 7]
# Selection SOrt

def selection_sort(my_List):
    
    for i in range(len(my_List)-1):
        min_index = i
        for j in range(i+1, len(my_List)):
            if my_List[j]<my_List[min_index]:
                min_index = j
        temp = my_List[i]
        my_List[i] = my_List[min_index]
        my_List[min_index] = temp
        
        
    return my_List

print(selection_sort([4,6,2,1,9,4,3,5,7,8]))
[1, 2, 3, 4, 4, 5, 6, 7, 8, 9]
# insertion Sort

def insertion_sort(my_List):
    for i in range(1,len(my_List)):
        temp = my_List[i]
        j = i-1
        while temp<my_List[j] and j>-1:
            my_List[j+1] = my_List[j]
            my_List[j] = temp
            j-=1
    return my_List

print(insertion_sort([8,5,4,6,2,9,1,7,2]))
[1, 2, 2, 4, 5, 6, 7, 8, 9]
# Merge Sort 
# When two list and combined two lists

def merge(list1,list2):
    combined = []
    i = 0
    j = 0
    while i <len(list1) and j < len(list2):
        if list1[i]<list2[j]:
            combined.append(list1[i])
            i +=1
        else:
            combined.append(list2[j])
            j +=1
    while i <len(list1):
        combined.append(list1[i])
        i += 1
    while j< len(list2):
        combined.append(list2[j])
        j+=1
    return combined
                         
print(merge([1,3,5,7,9],[2,4,6,8,10]))
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
# W
 
