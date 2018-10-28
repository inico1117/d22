# d22

>> A = struct('data',[3 4 7;8 0 1],'nest',...
struct('testnum','Test 1',...
'xdata',[4 2 8],'ydata',[7 1 6]));
>> A(2).data = [9 3 2;7 6 5];
>> A(2).nest.testnum = 'Test 2';
>> A(2).nest.xdata = [3 4 2];
>> A(2).nest.ydata = [5 0 9];
>> A(2)

ans = 

  包含以下字段的 struct:

    data: [2×3 double]
    nest: [1×1 struct]

>> A

A = 

  包含以下字段的 1×2 struct 数组:

    data
    nest

>> A(1,1) = {[1 4 3;0 5 8;7 2 9]};
>> A(1,2) = {'Anne Smith'};
>> A(2,1) = {3+7i};
>> A(2,2) = {-pi:pi:pi};
>> A

A =

  2×2 cell 数组

    {3×3 double        }    {'Anne Smith'}
    {[3.0000 + 7.0000i]}    {1×3 double  }

>> B{1,1} = 'This is the first cell';
>> B{1,2} = [5+j*6 4+j*5];
>> B{2,1} = [1 2 3;4 5 6;7 8 9];
>> B{2,2} = {'Tim','Chris'};
>> B

B =

  2×2 cell 数组

    {'This is the first cell'}    {1×2 double}
    {3×3 double              }    {1×2 cell  }

>> a = magic(3)

a =

     8     1     6
     3     5     7
     4     9     2

>> b = num2cell(a)

b =

  3×3 cell 数组

    {[8]}    {[1]}    {[6]}
    {[3]}    {[5]}    {[7]}
    {[4]}    {[9]}    {[2]}

>> c = mat2cell(a,[1 1 1],3)

c =

  3×1 cell 数组

    {1×3 double}
    {1×3 double}
    {1×3 double}

>> d = mat2cell(a,[1 0 2],[1 1 1])

d =

  3×3 cell 数组

    {[       8]}    {[       1]}    {[       6]}
    {0×1 double}    {0×1 double}    {0×1 double}
    {2×1 double}    {2×1 double}    {2×1 double}

>> a = [1 2;3 4];
>> b = [5 6;7 8];
>> cat(1,a,b)

ans =

     1     2
     3     4
     5     6
     7     8

>> cat(2,a,b)

ans =

     1     2     5     6
     3     4     7     8

>> cat(3,a,b)

ans(:,:,1) =

     1     2
     3     4


ans(:,:,2) =

     5     6
     7     8

>> A{1,1} = [1 2;4 5];
>> A{1,2} = 'Name';
>> A{2,1} = 2-4i;
>> A{2,2} = 7;
>> B{1,1} = 'Name2';
>> B{1,2} = 3;
>> B{2,1} = 0:1:3;
>> B{2,2} = [4 5]';
>> cat(3,A,B)

  2×2×2 cell 数组

ans(:,:,1) = 

    {2×2 double        }    {'Name'}
    {[2.0000 - 4.0000i]}    {[   7]}


ans(:,:,2) = 

    {'Name2'   }    {[       3]}
    {1×4 double}    {2×1 double}

>> A = {'James Bond',[1 2;3 4;5 6];pi,magic(5)}

A =

  2×2 cell 数组

    {'James Bond'}    {3×2 double}
    {[    3.1416]}    {5×5 double}

>> reshape(A,1,4)

ans =

  1×4 cell 数组

    {'James Bond'}    {[3.1416]}    {3×2 double}    {5×5 double}
>> B = [1:3;4:6]

B =

     1     2     3
     4     5     6

>> reshape(B,3,2)

ans =

     1     5
     4     3
     2     6
