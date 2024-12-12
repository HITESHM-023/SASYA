4. 
package main
import "fmt"
func main() {
	var n int
	fmt.Print("Enter a number: ")
	if _, err := fmt.Scan(&n); err != nil {
		fmt.Println("Invalid input.")
	} else if n >= 1 && n <= 10 {
		fmt.Println("The number is between 1 and 10.")
	} else {
		fmt.Println("The number is not between 1 and 10.")
	}
}
----------------------------------------------------x--------------------------x----------------------------------
5.Write a Go a program which creates an array with the number 0 to 10. 

package main
import "fmt"
func main() {
	var numbers [11]int
	for i := range numbers {
		numbers[i] = i
	}
	for _, num := range numbers {
		fmt.Println(num)
	}
}
----------------------------------------------------x--------------------------x----------------------------------
6.SUM OF 1 TO 10
package main
import "fmt"
func main() {
 var sum float32 = 0
 var i float32 = 1
 for i <= 10 {
 sum = sum + i
 i = i + 1
 }
 fmt.Println("sum of 1 to 10 numbers is ", sum)
} 
----------------------------------------------------x--------------------------x----------------------------------
7. Truncate

package main
import "fmt"
func main() {
 var f float64
 fmt.Println("Enter a float:")
 fmt.Scanln(&f)
 i := int(f)
 fmt.Println("Truncated integer:", i)
} 
----------------------------------------------------x--------------------------x----------------------------------
8. Checking Existence of Char

package main
import "fmt"
import "strings"

func main() {
 str := "I am a batman"
 if strings.HasPrefix(str, "I") && strings.HasSuffix(str, "n") && strings.Contains(str,"a") {
 fmt.Println("String found : ", str)
 } else {
 fmt.Println("String not found : ", str)
 }
} 
----------------------------------------------------x--------------------------x----------------------------------
9. Write a Go a program to check if a file exists on your local disk or not

package main
import "fmt"
import "os"
func main() {
 filePath := "/home/nmit/a.py"
 if _, err := os.Stat(filePath); os.IsNotExist(err) {
 fmt.Printf("File does not exist: %s\n", filePath)
 } else if err != nil {
 fmt.Printf("Error checking file: %s\n", err)
 } else {
 fmt.Printf("File exists: %s\n", filePath)
 }
}
----------------------------------------------------x--------------------------x----------------------------------
10. Write a Go a program to write a list of cities to a new file. 

package main
import "fmt"
import "os"

func main() {
 newCities := []string{ "London", "Paris", "Rome", "Berlin", "Madrid"}
 file, err := os.Create("new_cities.txt")
 if err != nil {
 panic(err)
 }
 defer file.Close()
 for _, city := range newCities {
 fmt.Fprintf(file, "%s\n", city)
 }
 fmt.Println("List of new cities saved to new_cities.txt")
}
---------------------------------------------------x--------------------------x----------------------------------
11. Write a Go a program that takes the string ‘hello world’ and slice it in two .

package main
import "fmt"

func main() {
 str := "hello world"
 mid := len(str) / 2
 firstPart := str[:mid]
 secondPart := str[mid:]
 fmt.Println("First part:", firstPart)
 fmt.Println("Second part:", secondPart)
} 
----------------------------------------------------x--------------------------x----------------------------------
12. Add 2 num

package main
import "fmt"

func sum(a int, b int) int {
 return a + b
}
func main() {
 var num1, num2 int
 fmt.Print("Enter the first number: ")
 fmt.Scanf("%d", &num1)
 fmt.Print("Enter the second number: ")
 fmt.Scanf("%d", &num2)
 result := sum(num1, num2)
 fmt.Printf("The sum of %d and %d is: %d\n", num1, num2, result)
} 
----------------------------------------------------x--------------------------x----------------------------------
13. CALCI

package main
import (
 "fmt"
)

func add(a int, b int) int {
 return a + b
}

func calculateAndPrint(num1 int, num2 int) {
 result := add(num1, num2)
 fmt.Printf("The sum of %d and %d is: %d\n", num1, num2, result)
}

func main() {
 var num1, num2 int
 fmt.Print("Enter the first number: ")
 fmt.Scanf("%d", &num1)
 fmt.Print("Enter the second number: ")
 fmt.Scanf("%d", &num2)
 calculateAndPrint(num1, num2)
} 
----------------------------------------------------x--------------------------x----------------------------------
14. INSERT AND SORT

package main
import "fmt"
import "sort"

func main() {

 numbers := []int{}
 for {
 var input string
 fmt.Print("Enter an integer (or 'X' to exit): ")
 fmt.Scan(&input)
 if input == "X" || input == "x" {
 break
 }

 var number int
 _, err := fmt.Sscanf(input, "%d", &number)
 if err != nil {
 fmt.Println("Invalid input. Please enter an integer.")
 continue
 }

 numbers = append(numbers, number)
 sort.Ints(numbers)
 fmt.Println("Sorted numbers:", numbers)
 }
}
----------------------------------------------------x--------------------------x----------------------------------

15. Write a Go program which prompts the user to first enter a name, and then enter an
address. Your program should create a map and add the name and address to the map
using the keys “name” and “address”, respectively. Your program should use Marshal()
to create a JSON object from the map, and then your program should print the JSON
object. 

package main
import "encoding/json"
import "fmt"

func main() {
 data := make(map[string]string)
 fmt.Print("Enter your name: ")
 var name string
 fmt.Scanln(&name)
 fmt.Print("Enter your address: ")
 var address string
 fmt.Scanln(&address)
 data["name"] = name
 data["address"] = address
 jsonData, err := json.Marshal(data)
 if err != nil {
 fmt.Println("Error marshaling to JSON:", err)
 return
 }
 fmt.Println("JSON object:", string(jsonData))
} 
