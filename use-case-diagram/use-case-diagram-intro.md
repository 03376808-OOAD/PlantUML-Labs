# Use Case Diagram

Plant UML มีความสามารถในการรองรับการเขียน use case diagram ทั้งในส่วนของ use case, actor, การเปลี่ยนลูกศรเป็นแบบต่างๆ 

Reference : [https://plantuml.com/use-case-diagram](https://plantuml.com/use-case-diagram)

## แนะนำการเขียน use case โดยใช้ plantuml

---

### 1.การเขียน Use cases

การเขียน use case ทำได้โดยการเขียนชื่อ use case ไว้ในวงเล็บ ( ) ซึ่งถ้าดูรูปจะคล้ายกับรูปวงรี
นอกจากการใช้วงเล็บ อาจจะเขียนคีย์เวิร์ด `usecase` นำหน้าชื่อ use case ที่ต้องการ

``` text
@startuml
' ระบุ use case โดยใช้เครื่องหมายวงเล็บ
(First usecase)  

' ระบุ use case โดยใช้เครื่องหมายวงเล็บ และกำหนดชื่อให้เป็น UC2 
' ในการอ้างถึงในด้านล่างของโปรแกรม เราสามารถใช้ได้ทั้งชื่อ use case และชื่อตัวแปร
(Another usecase) as (UC2)

' สร้าง use case ชื่อ UC3 โดยใชีคีย์เวิร์ด (ไม่ใช้วงเล็บ) 
usecase UC3

' สร้าง use case ที่มีข้อความ 2 บรรทัด และกำหนดชื่อตัวแปรเป็น UC4
usecase (Last\nusecase) as UC4
@enduml
```

จาก code ด้านบนจะถูกวาดเป็นไดอะแกรมตามรูปที่ 1

![รูปที่ 1 การวาด use case](./image/diagram1.png)

รูปที่ 1 การวาด use case

---

### 2.การเขียน Actors

* การเขียน actor ทำได้โดยการเขียนคร่อมด้วนเครื่องหมาย colon ทั้งสองด้าน
* หรือเขียนตามหลังคีย์เวิร์ด actor ก็ได้
* เราสามารถกำหนดชื่อตัวแปรให้กับ actor  เพื่อความสะดวกในการเรียกใช้งานในภายหลัง โดยใช้คีย์เวิร์ด as 

```text
@startuml
' เขียน actor โดยวิธีการปกติ (ล้อมรอบด้วย colon :___: )
:First Actor:

' เขียน actor โดยวิธีการปกติ พร้อมกำหนดชื่อตัวแปร
:Another\nactor: as Men2

' เขียน actor โดยใช้คีย์เวิร์ด actor
actor Men3

' เขียน actor โดยวิธีการปกติ พร้อมกำหนดชื่อตัวแปร
actor :Last actor: as Men4
```

จาก code ด้านบนจะถูกวาดเป็นไดอะแกรมตามรูปที่ 2

![รูปที่ 2 การวาด actor](./image/diagram2.png)

รูปที่ 2 การวาด actor

---

### 3.การเขียน Usecases description

* ถ้าชื่อ use case มีข้อความที่ยาวหลายบรรทัด 
* เราสามารถเขียนล้อมรอบด้วยเครื่องหมายคำพูด ("  ")  
* สามารถใช้เครื่องหมายต่อไปนี้เพื่อแบ่งส่วนย่อย (separator) ของ use case 
  * --
  * ..
  * ==
  * __
* สามารถใส่  title ในตัวแบ่งส่วนได้

พิจารณาจากตัวอย่างต่อไปนี้

``` text
@startuml
usecase UC1 as "You can use
several lines to define your usecase.
You can also use separators.
--
Several separators are possible.
==
And you can add titles:
..Conclusion..
This allows large description."

@enduml
```

จาก code ด้านบนจะถูกวาดเป็นไดอะแกรมตามรูปที่ 3

![รูปที่ 3 การเขียน Usecases description](./image/diagram3.png)

รูปที่ 3 การเขียน Usecases description

### 4.การเขียน Extension

Actor หรือ use case สามารถทำ inheritance ได้
เราสามารถใช้เครื่องหมาย  <|-- เพื่อแสดง inheritance 

``` text
@startuml
:Main Admin: as Admin
(Use the application) as (Use)

User <|-- Admin
(Start) <|-- (Use)

@enduml
```

จาก code ด้านบนจะถูกวาดเป็นไดอะแกรมตามรูปที่ 4

![รูปที่ 4 การเขียน Extension](./image/diagram4.png)

รูปที่ 4 การเขียน Extension

---

### 5.การเขียน notes

ใน plantuml เราสามารถเขียน note เพื่ออธิบายส่วนประกอบต่างๆ หรือให้ข้อมูลเพิ่มเติมแก่ผู้ใช้งาน use case diagram ได้  

โดยที่ note สามารถเขียนไว้ที่ด้านซ้าย ขวา บน หรือ ล่าง ขององค์ประกอบอื่นๆ หรือเขียนไว้ต่างหาก แล้วเชื่อมไปยังองค์ประกอบที่ต้องการ โดยใช้เครื่องหมาย ..

``` text
@startuml
:Main Admin: as Admin
(Use the application) as (Use)

User -> (Start)
User --> (Use)

Admin ---> (Use)

note right of Admin : This is an example.

note right of (Use)
  A note can also
  be on several lines
end note

note "This note is connected\nto several objects." as N2
(Start) .. N2
N2 .. (Use)
@enduml

```

จาก code ด้านบนจะถูกวาดเป็นไดอะแกรมตามรูปที่ 5

![รูปที่ 5 การเขียน notes](./image/diagram5.png)

รูปที่ 5 การเขียน notes

---
