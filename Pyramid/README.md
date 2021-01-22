# Scenario
Listen to this story: a boy and his father, a computer programmer, are playing with wooden blocks. They are building a pyramid.

<br/>

Their pyramid is a bit weird, as it is actually a pyramid-shaped wall - it's flat. The pyramid is stacked according to one simple principle: each lower layer contains one block more than the layer above.

<br/>

The figure illustrates the rule used by the builders:

![](https://edube.org/uploads/media/default/0001/01/26238ebafe7c913f177040785f30d7dde4a1c69a.png)

<br/>

Your task is to write a program which reads the number of blocks the builders have, and outputs the height of the pyramid that can be built using these blocks.

<br/>

Note: the height is measured by the number of fully completed layers - if the builders don't have a sufficient number of blocks and cannot complete the next layer, they finish their work immediately.

Test your code using the data we've provided.

<br/>

# Test Data

Sample input: 6

Expected output: The height of the pyramid: 3

---

Sample input: 20

Expected output: The height of the pyramid: 5

---

Sample input: 1000

Expected output: The height of the pyramid: 44

---

Sample input: 2

Expected output: The height of the pyramid: 1

---

<br/>
<br/>
<br/>

# Here my solution

```Python
# Input the first value
blocks = (int(input('Enter a number of blocks:')))
# I use this variable as a independent counter 
counter = 0
# Our height counter 
height = 0

# If the blocks is not equal to counter
# we will continue
while blocks != counter:
    print('plus one level')
    # We have counter and height 0. 
    # Now every time we will add +1
    # like counter(0)=counter(0)+1+height(0)=counter(1)
    counter += 1 + height
    # height(0)=height(0)+1=height(1)
    height += 1


    # Next lopp we will have counter=1 where we have instruction +1 + height(1)     \\height here in the end it gains = 2
    # Next loop counter=3, we look in instruction +1 +height=2  \\height here in the end it gains = 3
    # Next loop counter=6 + 1 in instruction + height3
    # Next loop counter=10 + 1 in instruction + height4
    # Next loop counter=15 + 1 in instruction + height5
    # Next loop counter=21 + 1 in instruction + height6


    # In the end if we have input in block value 20
    # mean counter=15 + 1 in instruction + height5 = 21
    # what more or equal to blocks(20). We can We can build only 5 levels in height.

    #Its need to stop the loop, because we don't have enough blocks.
    if counter + height >= blocks:
        break
print('The height of the pyramid:', height)