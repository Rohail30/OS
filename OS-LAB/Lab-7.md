
## Function Declaration

```bash
function testFunc() {
    echo "Hello World"
}

testFunc
```

Declares a function named `testFunc` that prints "Hello World" when called and then calls the function.

## IF / ELSE Statement

```bash
read num

if [ $num -gt 10 ]; then
    echo "The number is greater than 10"
elif [ $num -eq 10 ]; then
    echo "The number is equal to 10"
else
    echo "The number is less than 10"
fi
```

Reads a number from the user and checks if it is greater than, equal to, or less than 10, printing a corresponding message.

## FOR Loop (Printing Array Elements)

```bash
arr=(1 2 3)

for i in ${arr[@]}; do
    echo $i
done
```

Iterates through the elements of the array `arr` and prints each element.

## WHILE Loop (Printing Numbers from 1 to 10)

```bash
i=1
while [ $i -le 10 ]; do
    echo $i
    let i=i+1
done
```

Uses a while loop to print numbers from 1 to 10.

Feel free to customize the wording and formatting based on your preferences.
