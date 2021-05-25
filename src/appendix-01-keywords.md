## ภาคผนวก A: คีย์เวิร์ด

รายชื่อต่อไปนี้ประกอบด้วยคีย์เวิร์ดที่สงวนเอาไว้สำหรับการใช้งานในปัจจุบันและอนาคตด้วยภาษา Rust
ด้วยเหตุนี้จึงไม่สามารถใช้เป็น identifiers ได้ (ยกเว้นใช้เป็น
Identifiers][raw-identifiers]<!-- ignore -->” ), รวมถึงชื่อของ
ฟังก์ชัน, ตัวแปร, พารามิเตอร์, struct fields, โมดูล, crates, ค่าคงที่,
macro, static values, attributes, types, traits, หรือ lifetimes.

[raw-identifiers]: #raw-identifiers

### คีย์เวิร์ดที่ใช้อยู่ในปัจจุบัน 

คีย์เวิร์ดเหล่านี้ในปัจจุบันมีการทำงานดังนี้

* `as` - perform primitive casting, disambiguate the specific trait containing
  an item, or rename items in `use` and `extern crate` statements
* `async` -  return a `Future` instead of blocking the current thread
* `await` - suspend execution until the result of a `Future` is ready
* `break` - exit a loop immediately
* `const` - define constant items or constant raw pointers
* `continue` - continue to the next loop iteration
* `crate` - link an external crate or a macro variable representing the crate in
  which the macro is defined
* `dyn` - dynamic dispatch to a trait object
* `else` - fallback for `if` and `if let` control flow constructs
* `enum` - define an enumeration
* `extern` - link an external crate, function, or variable
* `false` - Boolean false literal
* `fn` - define a function or the function pointer type
* `for` - loop over items from an iterator, implement a trait, or specify a
  higher-ranked lifetime
* `if` - branch based on the result of a conditional expression
* `impl` - implement inherent or trait functionality
* `in` - part of `for` loop syntax
* `let` - bind a variable
* `loop` - loop unconditionally
* `match` - match a value to patterns
* `mod` - define a module
* `move` - make a closure take ownership of all its captures
* `mut` - denote mutability in references, raw pointers, or pattern bindings
* `pub` - denote public visibility in struct fields, `impl` blocks, or modules
* `ref` - bind by reference
* `return` - return from function
* `Self` - a type alias for the type we are defining or implementing
* `self` - method subject or current module
* `static` - global variable or lifetime lasting the entire program execution
* `struct` - define a structure
* `super` - parent module of the current module
* `trait` - define a trait
* `true` - Boolean true literal
* `type` - define a type alias or associated type
* `union` - define a [union] and is only a keyword when used in a union declaration
* `unsafe` - denote unsafe code, functions, traits, or implementations
* `use` - bring symbols into scope
* `where` - denote clauses that constrain a type
* `while` - loop conditionally based on the result of an expression

[union]: ../reference/items/unions.html

### คีย์เวิร์ดที่สงวนไว้สำหรับการใช้งานในอนาคต

คีย์เวิร์ดต่อไปนี้ไม่มีการทำงานใดๆ แต่ Rust สงวนไว้สำหรับการใช้งานในอนาคต 

* `abstract`
* `become`
* `box`
* `do`
* `final`
* `macro`
* `override`
* `priv`
* `try`
* `typeof`
* `unsized`
* `virtual`
* `yield`

### Raw Identifiers

*Raw identifiers* คือ syntax ที่ให้คุณใช้คีย์เวิร์ดในที่ที่ปกติจะไม่ได้รับอนุญาต
คุณสามารถใช้ raw identifier โดยการใส่ `r#` ไว้ข้างหน้าคีย์เวิร์ด

ตัวอย่างเช่น `match` เป็นคีย์เวิร์ด ถ้าคุณฦลองคอมไพล์ฟังก์ชันเหล่านี้
ซึ่งใช้ `match` เป็นชื่อของฟังก์ชัน:

<span class="filename">ชื่อไฟล์: src/main.rs</span>

```rust,ignore,does_not_compile
fn match(needle: &str, haystack: &str) -> bool {
    haystack.contains(needle)
}
```

คุณจะได้รับข้อผิดพลาดนี้:

```text
error: expected identifier, found keyword `match`
 --> src/main.rs:4:4
  |
4 | fn match(needle: &str, haystack: &str) -> bool {
  |    ^^^^^ expected identifier, found keyword
```

ข้อผิดพลาดนี้แสดงให้เห็นว่าคุณไม่สามารถใช้คียเวิร์ด `match` as the function
identifier. เพื่อจะใช้ `match` เป็นชื่อของฟังก์ชัน, คุณจำเป็นจะต้องใช้ raw
identifier syntax แบบนี้:

<span class="filename">ชื่อไฟล์: src/main.rs</span>

```rust
fn r#match(needle: &str, haystack: &str) -> bool {
    haystack.contains(needle)
}

fn main() {
    assert!(r#match("foo", "foobar"));
}
```

โค้ดนี้จะคอมไพล์โดยไม่มีข้อผิดพลาด, โปรดสังเกตุว่าคำนำหน้า `r#` อยู่ในชื่อของฟังก์ชันในขณะที่สร้าง
และเมื่อเรียกใช้ใน `main`.

Raw identifiers อนุญาตให้คุณใช้คำไหนก็ได้เป็น identifier
แม้ว่าคำนั้นจะเป็นคีย์เวิร์ดที่สงวนไว้ก็ตาม นอจากนี้ raw identifiers
อนุญาตให้คุณเรียกใช้ไลบรารีที่เขียนในรุ่นที่แตกต่างจากรุ่น Rust ที่ใช้อยู่
ตัวอย่างเช่น `try` ไม่ใช่คีย์เวิร์ดในรุ่นปี 2015 แต่เป็นคีย์เวิร์ดในรุ่นปี 2018
และถ้าคุณต้องการใช้ไลบรารีที่เขียนโดยใช้รุ่นของปี 2015
และมีฟังก์ชัน `try` คุณจำเป็นจะต้องใช้ raw identifier syntax `r#try` in
ในกรณี่ที่เรียกฟังก์ชันจากโค้ดในรุ่นปี 2018 ดูที่ [ภาคผนวก
E][appendix-e]<!-- ignore --> สำหรับข้อมูลเพิ่มเติมเกี่ยวกับรุ่นต่างๆ

[appendix-e]: appendix-05-editions.html
