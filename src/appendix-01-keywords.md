## ภาคผนวก A: คีย์เวิร์ด

รายชื่อต่อไปนี้ประกอบด้วยคีย์เวิร์ดที่สงวนเอาไว้สำหรับการใช้งานในปัจจุบันและอนาคตด้วยภาษา Rust
ด้วยเหตุนี้จึงไม่สามารถใช้เป็น identifiers ได้ (ยกเว้นใช้เป็น
raw identifiers ซึ่งเราจะพูดถึงในส่วน “[Raw
Identifiers][raw-identifiers]<!-- ignore -->” ), รวมถึงชื่อของ
ฟังก์ชัน, ตัวแปร, พารามิเตอร์, struct fields, โมดูล, crates, ค่าคงที่,
มาโคร, static values, attributes, types, traits, หรือ lifetimes.

[raw-identifiers]: #raw-identifiers

### คีย์เวิร์ดที่ใช้อยู่ในปัจจุบัน 

คีย์เวิร์ดเหล่านี้ในปัจจุบันมีการทำงานดังนี้


* `as` - ดำเนินการแปลง primitive, ลดความกำกวมของ trait ที่มีไอเทมอยู่
  , หรือเปลี่ยนชื่อไอเทมใน `use` และ `extern crate`
* `async` -  คืนค่า `Future` แทนที่จะบล็อกเธรด (Thread) ปัจจุบัน
* `await` - หยุดการทำงานจนกว่าผลของ `Future` จะพร้อม
* `break` - ออกจากการวนรอบทันที
* `const` - กำหนด constant items หรือ constant raw pointers
* `continue` - ไปยังการวนรอบถัดไป
* `crate` - ลิงค์ไปยัง crate ภายนอกหรือตัวแปรมาโครที่แทน crate
  ที่มาโครถูกกำหนด
* `dyn` - dynamic dispatch ไปยังออบเจกต์ trait
* `else` - ส่วนต่อท้ายสำหรับโครงสร้างเงื่อนไข `if` และ `if let`
* `enum` - กำหนด enumeration
* `extern` - ลิงค์ไปยัง crate ภายนอก, ฟังก์ชัน, หรือตัวแปร
* `false` - บูลีนค่าเท็จ
* `fn` - กำหนดฟังก์ชัน (function) หรือ function pointer type
* `for` - วนซ้ำไอเทมจาก iterator, implement trait, หรือระบุ
  higher-ranked lifetime
* `if` - เงื่อนไขการทำงานขึ้นอยู่กับผลของ expression
* `impl` - ใช้ฟังก์ชันของตัวเองหรือฟังก์ชันจาก trait
* `in` - ส่วนหนึ่งของการกำหนดการวนรอบ `for`
* `let` - ผูกตัวแปร
* `loop` - วนรอบอย่างไม่มีเงื่อนไข
* `match` - จับคู่ค่ากับรูปแบบ
* `mod` - กำหนดโมดูล (module)
* `move` - ทำให้ closure รับความเป็นเจ้าของ (ownership) ของ captures ทั้งหมด
* `mut` - ใช้แสดงถึงความสามารถในการการแก้ไขได้ (mutability) ใน references, raw pointers, หรือ pattern bindings
* `pub` - ใช้แสดงการมองเห็นในระดับ public ใน fields ของ struct ,บล็อกของ `impl`, หรือโมดูล
* `ref` - ผูกโดยตัวอ้างอิง (reference)
* `return` - คืนค่าจากฟังก์ชัน
* `Self` - type alias สำหรับ type ที่เรากำหนดไว้หรือ implementing
* `self` - method subject หรือโมดูลปัจจุบัน
* `static` - global variable หรือมี lifetime อยู่จนโปรแกรมทำงานเสร็จสิ้น
* `struct` - กำหนดสตรักเจอร์ (structure)
* `super` - parent module ของโมดูลปัจจุบัน
* `trait` - กำหนด trait
* `true` - บูลีนค่าจริง
* `type` - กำหนด type alias หรือ associated type
* `union` - กำหนด [union] และเป็นเพียงคีย์เวิร์ดที่นำมาใช้ในการประกาศ union เท่านั้น
* `unsafe` - ใช้แสดงส่วน unsafe code, ฟังก์ชัน, traits, หรือ implementations
* `use` - นำสัญลักษณ์มาสู่ขอบเขต (scope)
* `where` - denote clauses that constrain a type
* `while` - วนรอบอย่างมีเงื่อนไขจากผลลัพธ์ของ expression


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
