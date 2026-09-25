# Hcl--Python-qp-25-09-26-
 ##  Task:
 ## 1  Student Attendance Analysis:

 # A college maintains the daily attendance details of its students in the form of a list containing student IDs. Some students may have attended multiple sessions on the same day. The administration wants to identify the longest continuous sequence of sessions in which no student ID is repeated. Develop a solution that determines the maximum length of such a sequence.

```
def max_unique_sessions(attendance):
    seen, left, max_len = {}, 0, 0
    for right, sid in enumerate(attendance):
        if sid in seen and seen[sid] >= left:
            left = seen[sid] + 1
        seen[sid] = right
        max_len = max(max_len, right - left + 1)
    return max_len

print(max_unique_sessions([101, 102, 103, 101, 104, 102]))
```

## 2 Online Shopping Price Analysis

# An online shopping application stores the prices of products viewed by a customer during a browsing session. The customer wants to identify a continuous range of products that provides the maximum possible total discount value. Given the discount values, determine the maximum value that can be obtained from any continuous range.
```
def max_discount(discounts):
    max_sum = discounts[0]
    n = len(discounts)
    
    for i in range(n):
        current_sum = 0
        for j in range(i, n):
            current_sum += discounts[j]
            if current_sum > max_sum:
                max_sum = current_sum
                
    return max_sum

print(max_discount([3, -2, 5, -1, 4, -2]))
```
## 3. Rainwater Collection System
# A city installs buildings of different heights along a straight road. During rainfall, water gets collected between taller buildings. The engineering team needs to calculate the total amount of water that can remain trapped after heavy rainfall based on the heights of the buildings.
```
def trap_water(height):
    left, right = 0, len(height) - 1
    left_max = right_max = water = 0

    while left < right:
        if height[left] < height[right]:
            if height[left] >= left_max:
                left_max = height[left]
            else:
                water += left_max - height[left]
            left += 1
        else:
            if height[right] >= right_max:
                right_max = height[right]
            else:
                water += right_max - height[right]
            right -= 1

    return water

print(trap_water([0, 1, 0, 2, 1, 0, 1, 3, 2, 1, 2, 1]))
```
## 4 Employee Performance Analysis
# A company stores the monthly performance scores of an employee for several months. The scores may contain both positive and negative values depending on the employee's performance. Management wants to identify the continuous period during which the employee achieved the highest overall performance.
``` 
def max_performance(scores):
    max_so_far = curr = scores[0]
    for s in scores[1:]:
        curr = max(s, curr + s)
        max_so_far = max(max_so_far, curr)
    return max_so_far

print(max_performance([5, -3, 2, 8, -6, 4]))
```
## 5
# A retail company stores the daily sales quantity of a product for several consecutive days. Due to seasonal changes, some days may have negative adjustments. The company wants to identify the period that produced the highest multiplication of sales-related values. Develop a solution to determine this maximum product.

```
def max_sales_product(sales):
    max_prod = min_prod = result = sales[0]

    for num in sales[1:]:
        if num < 0:
            max_prod, min_prod = min_prod, max_prod

        max_prod = max(num, max_prod * num)
        min_prod = min(num, min_prod * num)

        result = max(result, max_prod)

    return result

print(max_sales_product([2, 3, -2, 4]))       
print(max_sales_product([-2, 0, -1]))
print(max_sales_product([-2, 3, -4]))
 ```         
## 6. Customer Purchase History
# An e-commerce application stores the product IDs purchased by a customer in chronological order. The same product may appear multiple times. The system needs to determine the longest sequence of consecutive purchases in which every product ID is unique.
```
```
##  7. Bank Transaction Analysis
# A bank stores transaction amounts for a customer's account. A continuous group of transactions may add up to a specific target amount. The auditing system needs to determine how many different continuous transaction groups produce exactly the specified amount.
```
```
## 8. Employee Skill Grouping
# A company receives a list of employee skill codes represented as strings. Employees having the same set of characters in their skill codes belong to the same skill category, even if the characters appear in a different order. The HR system needs to organize employees into appropriate skill groups.
```
```
## 9. Network Packet Analysis
# A network monitoring system receives packet identifiers in chronological order. The system must determine the longest sequence of consecutive packets whose identifiers form a continuous numerical sequence, regardless of their original order in the incoming data.
```
```
## 10. Hospital Appointment Scheduling
# A hospital receives appointment requests represented by starting and ending times. Some appointments overlap with each other. The scheduling system needs to combine overlapping appointment periods so that the final schedule contains only non-overlapping time ranges.
```
```
