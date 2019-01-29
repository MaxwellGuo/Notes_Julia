# Introduction to Julia tutorials
## Getting started
>Key words: `println`, `typeof`, `convert`, `parse`
## Strings
### How to get a string
`"string"` and `"""stri"n"g"""`
> Note: ~~`'string'`~~,`'char'`
### String interpolation
```julia
stringname="string"
println("$stringname")
```
### String concatenation
```julia
stringname1="string1"
stringname2="string2"
string(stringname1,stringname2)# stringname1*stringname2
```
>Key words: `repeat`, string`^`N
## Data structures
| |Tuples|Dictionaries|Arrays|
 |-|-|-|-|
 |Mutablity|No|Yes|Yes|
|Orderlity|Yes|No|Yes|
 |Syntax|(item1, item2, ...)|Dict(key1 => value1, key2 => value2, ...)|[item1, item2, ...]|
|Key words| |`pop!`|`push!`, `pop!`, `copy`|

## Loops
### while loops
```julia
while *condition*
    *loop body*
end
```
### for loops
```julia
for *var* in *loop iterable*
    *loop body*
end
```
>key words: `fill`
 
## Conditionals
### with the if keyword
```julia
if *condition 1*
    *option 1*
elseif *condition 2*
    *option 2*
else
    *option 3*
end
```
### with ternary operators
```julia
a ? b : c
```
which equates to 
```julia
if a
    b
else
    c
end
```
### with short-circuit evaluation
```julia
a && b  # and
a || b  # or
```
>key words: `true`, `false`

## Functions
### How to declare a function
```julia
function functionname(arg)
   expression
end
```
or
```julia
functionname(arg)=expression
```
or
```julia
functionname=arg->fun(arg)
```
### Duck-typing in Julia
>"If it quacks like a duck, it's a duck." 

Julia functions will just work on whatever inputs make sense
### Mutating vs. non-mutating functions
functions followed by `!` alter their contents and functions lacking `! ` do not
>Key words: `sort`, `sort!`
 
### Some higher order functions
*takes a function as one of its input arguments*
#### map
```julia
map(f, [1, 2, 3])# [f(1), f(2), f(3)]
```
or
```julia
map(x -> f(x), [1, 2, 3]) 
```
#### broadcast
*`broadcast` is a generalization of `map`*
```julia
broadcast(f, [1, 2, 3])
```
or
```julia
f.([1, 2, 3])
```
>Note: ~~`vector^2`~~, `vector.^2`==`(every element of a vector)^2`

```julia
A .+ 2 .* f.(A) ./ A
```
or
```julia
broadcast(x -> x + 2 * f(x) / x, A)
```
or
```julia
@. A + 2 * f(A) / A
```
## Packages
```julia
using Pkg
Pkg.add("Name_Pkg")
using Name_Pkg
```
## Multiple dispatch

