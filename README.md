1.
a=input()
a=a.split(" ")


b=input()
count=0


for i in range (len(a)):
    if a[i].find(b):
        count+=1
if count>len(b):
    print(len(b))
else:
    print(count-1)

2.
def eliminate_common_elements(arr1, arr2):
    # Convert arrays to sets for efficient intersection and difference operations
    set1 = set(arr1)
    set2 = set(arr2)

    # Find non-repeating elements by taking the symmetric difference of the sets
    non_repeating_elements = set1.symmetric_difference(set2)

    # Print non-repeating elements
    for element in non_repeating_elements:
        print(element, end=" ")
    print()  # Move to the next line

    # Print total count of non-repeating elements
    print( len(non_repeating_elements))


# Input format:
# First line: size of arrays
# Second line: elements of the first array
# Third line: elements of the second array
size1, size2 = map(int, input().split())
arr1 = list(map(int, input().split()))
arr2 = list(map(int, input().split()))

# Call the function with input arrays
eliminate_common_elements(arr1, arr2)


3.
a=input()
c=0
for i in range(len(a)):
    if(a[i]=="0" or a[i]=="1"):
        c+=1
    
if(c==len(a)):
    print("Yes")
else:
    print("No")

4.
def count_distinct_pairs(t, K):
    pair_set = set()
    seen = set()
    count = 0
    
    for num in t:
        complement = K - num
        if complement in seen and (complement, num) not in pair_set and (num, complement) not in pair_set:
            pair_set.add((complement, num))
            count += 1
        seen.add(num)
    
    return count

t = tuple(int(x) for x in input().split(','))
K = int(input())

print(count_distinct_pairs(t, K))

5.
# Get input from the user
s = input()
sequence_length = 10

if len(s) < sequence_length:
    print()
else:
    seen = {}
    repeated = []
    
    for i in range(len(s) - sequence_length + 1):
        sequence = s[i:i + sequence_length]
        if sequence in seen:
            seen[sequence] += 1
            if seen[sequence] == 2:
                repeated.append(sequence)
        else:
            seen[sequence] = 1

    if not repeated:
        print("No repeated sequences.")
    else:
        for sequence in repeated:
            print(sequence)
