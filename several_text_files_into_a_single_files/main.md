echo "test1" > file1

cat file1
test1

echo "test2" > file2

cat file2
test2


#merging
cat file1 file2 > final

cat final
test1
test2

