# บทนำ

> Note: หนังสือเล่มนี้เป็นเล่มเดียวกับ [The Rust Programming
> Language][nsprust] สามารถหารูปแบบ print หรือ ebook ได้ที่ [No Starch
> Press][nsp].

[nsprust]: https://nostarch.com/rust
[nsp]: https://nostarch.com/

ยินดีต้อนรับเข้าสู่ *The Rust Programming Language*, หนังสือสำหรับการเริ่มต้นภาษา Rust.
ภาษาโปรแกรมมิ่ง Rust จะช่วยให้คุณเขียนโปรแกรมเร็วขึ้น และทำให้ Software ของคุณน่าเชื่อถือมากขึ้น.
รูปแบบภาษาของระดับสูงและระดับต่ำมักจะไม่สอดคล้องกันในด้านของภาษา programming ซึ่ง Rust ช่วยแก้ปัญหาตรงนี้ได้. 
ด้วยการรักษาสมดุลระหว่าง สมรรถภาพทางเทคนิค และประสบการการพัฒนาโปรแกรม Rust มีตัวเลือกให้ในการควบคุมรายละเอียดของระดับต่ำ(เช่น การใช้ memory) ซึ้งจะทำให้เรานั้นไม่ต้องไปยุ่งยากกับการควบคุมแบบเดิม.

## Rust เพื่อใคร

Rust สร้างมาเพื่อหลายๆกลุ่มคนในเหตุผลต่าง ไปดูกลุ่มที่สำคัญหลักๆกันเลยดีกว่า.

### สำหรับ Developer Team

Rust ได้พิสูจน์แล้วว่าเป็นเครื่องมือที่มีประสิทธิภาพสำหรับการทำงานร่วมกับทีมนักพัฒนาขนาดใหญ่ที่พัฒนาหรือออกแบบระบบในระดับต่างๆ. 
ในการ coding ภาษาระดับต่ำนั้นค่อนข้างจะเป็นเรื่องละเอียดอ่อนและง่ายต่อการเกิด Bug ซึ่งในหลายๆภาษาสามารถตรวจหาได้ด้วยการทำ extensive testing และผ่านการตรวจ code อย่างละเอียดโดยนักพัฒนาผู้มากประสบการณ์. 
ในภาษา Rust นั้น compiler จะทำหน้าที่เป็นนายประตูที่จะไม่ยอมให้ code ที่มี elusive bugs (bug ที่ตรวจจับได้ยาก) ผ่านไปได้, ซึ่งรวมไปถึง concurrency bugs ด้วยเช่นกัน. ในการทำงานควบคู่ไปกับ compiler นี้จะช่วยให้นักพัฒนาจดจ่อไปการวางตรรกะโดยที่ไม่ต้องคำนึงถึง bug.

Rust ยังได้นำเครื่องมือสำหรับการพัฒนามาช่วยในภาษาระบบด้วย:

* Cargo เครื่องมือช่วยในการจัดการ dependency และ build นอกจากนี้ยังเป็นเครื่องมือสำหรับ compile อีกด้วยแล้วยังเป็นตัวจัดการ dependency ที่ทำให้การจัดการง่ายขึ้นและมั่นคงตลอดทั่วทั้ง ecosystem ของ Rust.
* Rustfmt ช่วยให้รูปแบบการ coding สม่ำเสมอตลอดการพัฒนาโปรแกรม.
* The Rust Language Server ยังได้สนับสนุน Integrated Development Environment (IDE) สำหรับการบรรลุความสำเร็จในการ code และแสดงข้อความ error ในบรรทัดด้วย.

ถ้าหากว่าใช้เครื่องมือใน Rust ecosystem ละก็ developer จะมีประสิทธิภาพในการเขียนภาษาระดับ system-level code มากขึ้น.

### นักเรียน/นักศึกษา

สำหรับนักเรียน/นักศึกษาที่ในใจในระบบ 
มีผู้คนมากมายที่เรียนรู้ในหัวข้อเกี่ยวกับการพัฒนาระบบปฎิบัติการ 
และชุมชนของ Rust นั้นก็ยินดีที่จะต้อนรับและตอบคำถามของเหล่านักเรียน/นักศึกษาเสมอ. 
ด้วยการพยายามรวมทั้งการทำหนังสือเล่มนี้จากทีมงานของ Rust ซึ่งทางทีมงานนั้นอยากให้แนวคิดของระบบเข้าถึงได้ในหลายๆคนโดยเฉพาะผู้ฝึกหัดการ programming.

### บริษัท

หลายร้อยบริษัทไม่ว่าจะเล็กหรือใหญ่ ก็เลือกใช้ Rust ในการทำงาน production ในงานต่าง.
งานเหล่านั้นก็มีทั้ง command line tools, web services, DevOps tooling,
embedded devices, audio and video analysis and transcoding, cryptocurrencies,
bioinformatics, search engines, Internet of Things(IoT) applications, machine
learning, หรือแม้กระทั้งส่วนใหญ่ของ Firefox web browser ก็ยังใช้ Rust.

### Open Source Developers

Rust นั้นเป็นภาษาโปรแกรมมิ่งสำหรับทุกคนที่อยากจะพัฒนาภาษา Rust, สร้างชุมชน, สร้างเครื่องมือและ libraries สำหรับการพัฒนา. 
พวกเรานั้นยินดีเสมอที่จะมีคุณมามีส่วนร่วมในภาษา Rust.

### ผู้ที่ชื่นชอบในความเร็วและความเสถียร

Rust สำหรับคนที่โหยหาความเร็วและความเสถียร
ด้วยคำว่า "ความเร็ว" นั้นหมายถีงความเร็วของโปรแกรมที่เราจะสร้างด้วย Rust และ ความเร็วที่เราจะโปรแกรมด้วย Rust.
ในเรื่องของ "ความเสถียร" compiler ของ Rust จะรับรองความเสถียรภาพในการเพิ่ม feature และ refactoring code 
ซึ่งตรงกันข้ามกับหลักการ brittle legacy code (Code เก่าที่ยากที่จะเปลี่ยน) ซึ่งนักพัฒนาหลายคนมักจะไม่อยากดัดแปลงหรือแก้ไข
ด้วยการพยายามที่จะทำให้การ abstraction ไม่มีการศูนย์เสียเกิดขึ้น ภาษาระดับสูงจะถูก compile ให้เป็น Code ในภาษาระดับต่ำก่อนเพื่อให้เหมือนเขียน code ในภาษาระดับต่ำ ส่วนในภาษา Rust นั้นจะพยายามทำให้ code ปลอดภัยและเร็วเช่นกัน

ภาษา Rust นั้นความหวังว่าจะช่วยผู้ใช้อื่นเช่นกัน ที่กล่าวมาทั้งหมดนั้นเป็นเพียงบางส่วนของผู้มีส่วนได้ส่วนเสียที่ให่ที่สุด.
โดยรวมแล้วความปรารถณาของ Rust คือการกำจัดเงื่อนไขที่โปรแกรมเมอต้องยอมรับมากว่าทศวรรษเช่น การเลือกระหว่าง safety *และ* productivity, หรือระหว่าง ความเร็วในการเขียน *และ* ความง่ายในการเขียน. ลองมาเขียน Rust สิ แล้วมาดูกันว่าเข้ากับงานของคุณไหม.

## หนังสือเล่มนี้เหมาะกับใคร

หนังสือเล่มนี้จะคิดว่าคุณเคยเขียนภาษา programming อื่นมาแล้วแต่จะไม่สมมุติว่าคุณเขียนภาษาอะไรมา.
พวกเราได้พยายามทำเนื้อหาให้เข้าถึงได้อย่างกว้างขวางในหลายๆ programming backgrounds.
พวกเราจะไม่ใช้เวลาในการพูดถึงว่า programming *คือ* อะไรหรือคิดยังไง. ถ้าคุณเพิ่งเริ่มหัด programming มันจะดีกว่าถ้าคุณอ่านหนังสือเกียวกับการเริ่มต้น programming.

## How to Use This Book

In general, this book assumes that you’re reading it in sequence from front to
back. Later chapters build on concepts in earlier chapters, and earlier
chapters might not delve into details on a topic; we typically revisit the
topic in a later chapter.

You’ll find two kinds of chapters in this book: concept chapters and project
chapters. In concept chapters, you’ll learn about an aspect of Rust. In project
chapters, we’ll build small programs together, applying what you’ve learned so
far. Chapters 2, 12, and 20 are project chapters; the rest are concept chapters.

Chapter 1 explains how to install Rust, how to write a “Hello, world!” program,
and how to use Cargo, Rust’s package manager and build tool. Chapter 2 is a
hands-on introduction to the Rust language. Here we cover concepts at a high
level, and later chapters will provide additional detail. If you want to get
your hands dirty right away, Chapter 2 is the place for that. At first, you
might even want to skip Chapter 3, which covers Rust features similar to those
of other programming languages, and head straight to Chapter 4 to learn about
Rust’s ownership system. However, if you’re a particularly meticulous learner
who prefers to learn every detail before moving on to the next, you might want
to skip Chapter 2 and go straight to Chapter 3, returning to Chapter 2 when
you’d like to work on a project applying the details you’ve learned.

Chapter 5 discusses structs and methods, and Chapter 6 covers enums, `match`
expressions, and the `if let` control flow construct. You’ll use structs and
enums to make custom types in Rust.

In Chapter 7, you’ll learn about Rust’s module system and about privacy rules
for organizing your code and its public Application Programming Interface
(API). Chapter 8 discusses some common collection data structures that the
standard library provides, such as vectors, strings, and hash maps. Chapter 9
explores Rust’s error-handling philosophy and techniques.

Chapter 10 digs into generics, traits, and lifetimes, which give you the power
to define code that applies to multiple types. Chapter 11 is all about testing,
which even with Rust’s safety guarantees is necessary to ensure your program’s
logic is correct. In Chapter 12, we’ll build our own implementation of a subset
of functionality from the `grep` command line tool that searches for text
within files. For this, we’ll use many of the concepts we discussed in the
previous chapters.

Chapter 13 explores closures and iterators: features of Rust that come from
functional programming languages. In Chapter 14, we’ll examine Cargo in more
depth and talk about best practices for sharing your libraries with others.
Chapter 15 discusses smart pointers that the standard library provides and the
traits that enable their functionality.

In Chapter 16, we’ll walk through different models of concurrent programming
and talk about how Rust helps you to program in multiple threads fearlessly.
Chapter 17 looks at how Rust idioms compare to object-oriented programming
principles you might be familiar with.

Chapter 18 is a reference on patterns and pattern matching, which are powerful
ways of expressing ideas throughout Rust programs. Chapter 19 contains a
smorgasbord of advanced topics of interest, including unsafe Rust, macros, and
more about lifetimes, traits, types, functions, and closures.

In Chapter 20, we’ll complete a project in which we’ll implement a low-level
multithreaded web server!

Finally, some appendices contain useful information about the language in a
more reference-like format. Appendix A covers Rust’s keywords, Appendix B
covers Rust’s operators and symbols, Appendix C covers derivable traits
provided by the standard library, Appendix D covers some useful development
tools, and Appendix E explains Rust editions.

There is no wrong way to read this book: if you want to skip ahead, go for it!
You might have to jump back to earlier chapters if you experience any
confusion. But do whatever works for you.

<span id="ferris"></span>

An important part of the process of learning Rust is learning how to read the
error messages the compiler displays: these will guide you toward working code.
As such, we’ll provide many examples that don’t compile along with the error
message the compiler will show you in each situation. Know that if you enter
and run a random example, it may not compile! Make sure you read the
surrounding text to see whether the example you’re trying to run is meant to
error. Ferris will also help you distinguish code that isn’t meant to work:

| Ferris                                                                 | Meaning                                          |
|------------------------------------------------------------------------|--------------------------------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain"/>    | This code does not compile!                      |
| <img src="img/ferris/panics.svg" class="ferris-explain"/>              | This code panics!                                |
| <img src="img/ferris/unsafe.svg" class="ferris-explain"/>              | This code block contains unsafe code.            |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain"/>| This code does not produce the desired behavior. |

In most situations, we’ll lead you to the correct version of any code that
doesn’t compile.

## Source Code

The source files from which this book is generated can be found on
[GitHub][book].

[book]: https://github.com/rust-lang/book/tree/master/src
