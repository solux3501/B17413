import sys
input = sys.stdin.readline

N = int(input())
M = int(input())
data = list(input().rstrip())
num = 0
result = 0
stack = []
while M > num :
    temp = []
    if M > num and data[num] == "I" :
        temp.append("I")
        #print(data[num:num+2])
        while M > num and data[num+1:num+3] == ['O', 'I'] :
            num += 2
            temp.extend("OI")
    if len(temp) > 2 :
        stack.append(temp)
    num += 1

for i in stack :
    if len(i) >= 2*N + 1 :
        result += (len(i)+1)//2 - N
        #print(result)
    else :
        pass
print(result)
