def rotateMatrix(mat): 
  
    if not len(mat): 
        return
  
    top = 0
    bottom = len(mat)-1
  
    left = 0
    right = len(mat[0])-1
  
    while left < right and top < bottom: 
  
        prev = mat[top+1][left] 
  
        for i in range(left, right+1): 
            curr = mat[top][i] 
            mat[top][i] = prev 
            prev = curr 
  
        top += 1
  
        for i in range(top, bottom+1): 
            curr = mat[i][right] 
            mat[i][right] = prev 
            prev = curr 
  
        right -= 1
  
        for i in range(right, left-1, -1): 
            curr = mat[bottom][i] 
            mat[bottom][i] = prev 
            prev = curr 
  
        bottom -= 1
  
        for i in range(bottom, top-1, -1): 
            curr = mat[i][left] 
            mat[i][left] = prev 
            prev = curr 
  
        left += 1
  
    return mat 
  
def printMatrix(mat): 
    for row in range(n-1):
        for i in range(n):
            if(i!=n-1):
                print (mat[row][i],end=" " )
            else:
                print(mat[row][i],end="")
        print()
    for row in range(n-1,n):
        for i in range(n):
           print (mat[row][i],end=" " ) 


n=input()
n=int(n)
l=[]
for i in range(n):
    for j in range(1):
        temp=[int(g) for g in input().split()]
        l.append(temp)
  
matrix = rotateMatrix(l) 
# Print modified matrix 
printMatrix(matrix) 
