# test-circleci
Test repo for first tests of CircleCI


### Step 1: Let's create a simple GO project
For simplicity we just use `gb` to structure our project layout. More details can be found at http://getgb.io/docs/project/.

Create project structure
```
export PROJECT=$(pwd)
mkdir -p $PROJECT/src/hello
tree $PROJECT
```

Write a basic `Hello World` program
```
cat <<EOF > $PROJECT/src/hello/hello.go
package main
 
import "fmt"
 
func main() {
    fmt.Println("Hello gb")
}
EOF
tree $PROJECT
```

Now, compile and run it
```
gb build all
./bin/hello
tree $PROJECT
```


### Step 2: Define a CircleCI test and build
