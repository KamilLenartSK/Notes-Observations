## Values

- A value refers to a single unit of data
- Programming languages have different ways of representing values, depending on their type

## Types

- Types enable categorisation of values.
- Primitive types refers to the lowest level of how a value can be represented.
- Use typeof “value” to ask what kind of data “value” is representing
- typeof returns a string value !!!

**7 Fundamental Primitive types exist**

- NUMBER
- STRING
- BOOLEAN
- UNDEFINED
- NULL
- SYMBOL
- BIGINT

## Number Type

- Stored as 64 bit double precision floating point.
- NUMBER type can effortlessly handle most numeric values, including:

  - Positive integers
  - Negative integers
  - Floating point numbers
  - Special Cases:

    - -Infinity
    - +Infinity
    - NaN (Not a Number)

      - 0 / 0 ==> NaN
      - typeof NaN ==> Number
      - NaN indicates absence of **valid** numeric value
      - NaN is the only value that lacks identity - NaN === NaN is FALSE
        Utilities:

        1. isNaN() - performs implicit number coercion before attempting comparison

        2. Number.isNaN() - No coercion takes place BTS

## UNDEFINED vs UNDECLARED vs UNITIALISED

**UNDEFINED**

- variable identifier exists in memory however, its value has yet to be defined.

- in other words, a value assignment is yet to take place

- this behaviour is especially noticeable when utilising function-scoped identifiers, declared with **var** keyword

## ABSTRACT OPERATIONS

- these operations work behind-the-scenes and are not invocable directly

  1. **toPrimitive(value)**

     - This operation gets called internally by the JS engine whenever we have a non-primitive structure, such as arrays, and we would like to perform operation designated solely for primitive types, including concatenation or arithmetic ops.

     - value === **number**
       - invoke:
         - valueOf()
         - toString()
     - value === **string**
       - invoke:
         - toString()
         - valueOf()

  2. **toString(value)**

     - takes any value and returns its string equivalent:
       - null ==> “null”
       - undefined ==> “undefined”
       - true ==> “true”
       - false ==> “false”
       - 6 ==> “6”
       - 0 ==> “0”
       - -0 ==> “0”
       - For objects ==> [“object” Object]

  3. **toNumber(value)**

  - takes any value and converts it into a numeric equivalent
  - it strips out leading 0 and any white space characters
    - " " ==> 0
    - "0" ==> 0
    - "-0" ==> 0
    - “0.0” ==> 0
    - “009”==> 0
    - “3.14159” ==> 3.14159
    - “.” ==> NaN
    - “0xaf” ==> 175
    - False ==> 0
    - True ==> 1
    - Null ==> 0
    - Undefined ==> NAN
    - [“”] ==> 0

  4. **toBoolean(value)**

  - It only performs lookup to a **falsy** table to see if a value exists within it. If not, the value is regarded as **truthy**

  - **FALSY VALUES**:

    - “”
    - 0, -0
    - Null
    - NaN
    - False
    - Undefined

  - **TRUTHY VALUES**:

    - “foo”
    - 23
    - {a:1}
    - [1,3]
    - True
    - Function(){}

## Coercion

- plus operator **+**

  - If either one of the operands is a string, the plus operator prefers string concatenation
  - Unary + operator
    - Invokes **toNumber(value)** operation

- **toBoolean()** coercion:

  - Implicit with control statements

    - evaluation of **TRUTHY** and **FALSY** values

  - **!!** – this negates and flips the negation. In turn, the value's true boolean representation gets returned

## Abstract Equality Checking for types

- == checks value (loose)
- === checks the value and type
- They both check the types
- If the two values are same type, perform strict equality comparison == and === are the same
- Identity comparison not structure!!
- == allows coercion
- Null == undefined ==> coercive equality
- Double equals prefers reducing values to numbers to make the comparison
- If non primitive values are being compared, toPrimitive abstract operation gets invoked

- **AVOID** :
  - == with 0 , “” or even “ “
  - == with non-primitives
  - == true or == false : allow toBoolean
