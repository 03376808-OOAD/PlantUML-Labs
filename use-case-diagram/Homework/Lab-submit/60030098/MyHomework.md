#การบ้าน (Homework)
##ของนายสิทธินนท์ ตติยะจินดา รหัสนักศึกษา 60030098

จากคำสั่งของอาจารย์
กระผมจึงได้เขียน Code ของ PlantUML ดังนี้

1.ระบบจัดการร้านอาหาร

1.1

```
@startuml food1
actor customer
actor Owner
left to right direction
skinparam rectangle{    
    FontColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam actor{
    FontColor #73ae42
    BackgroundColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam usecase {
    FontColor White 
    ArrowColor #5b9bd5
    BackgroundColor #5b9bd5
    BorderColor #5b9bd5
    Shadowing false
}
rectangle "Online Food shop overview"{
    customer -- (Member register)
    customer -- (Log in)
    (Manage Goods) -- Owner
    (Log in) -- Owner
    customer -- (Make Order)
    (Print Slips) -- Owner
}
@enduml
```

1.2

```
@startuml food2
actor customer
actor Owner
left to right direction
skinparam rectangle{    
    FontColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam actor{
    FontColor #73ae42
    BackgroundColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam usecase {
    FontColor White 
    ArrowColor #5b9bd5
    BackgroundColor #5b9bd5
    BorderColor #5b9bd5
    Shadowing false
}
rectangle "Online Food shop menu management subsystem"{
    (Add food menu) -- Owner
    (Edit menu) -- Owner
    customer -- (View menu)
    (View menu) -- Owner
}
@enduml
```

1.3
```
@startuml food3
actor customer
actor supervisor
left to right direction
skinparam rectangle{    
    FontColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam actor{
    FontColor #73ae42
    BackgroundColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam usecase {
    FontColor White 
    ArrowColor #5b9bd5
    BackgroundColor #5b9bd5
    BorderColor #5b9bd5
    Shadowing false
}
rectangle "Online Food shop order subsystem"{
    customer -- (Select items)
    customer -- (make order)
    (check order) -- supervisor
    (make purchase order) -- supervisor
}
@enduml
```

1.4
```
@startuml truck
actor employee
actor Admin
actor :Truck Manager: as Truck
left to right direction
skinparam rectangle{    
    FontColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam actor{
    FontColor #73ae42
    BackgroundColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam usecase {
    FontColor White 
    ArrowColor #5b9bd5
    BackgroundColor #5b9bd5
    BorderColor #5b9bd5
    Shadowing false
}
rectangle "Online Food shop menu management subsystem"{
    employee -- (Login)
    (Login) -- Admin
    (Manage employee) -- Admin
    (Rent Truck<U+0028>s<U+0029>) -- employee
    (Manage Truck Info) -- Truck
    (Release a truck) -- Truck
    (Invoice manage) -- Truck
}
@enduml
```

1.5
```
@startuml book
actor Customer
actor Employee
left to right direction
skinparam rectangle{    
    FontColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam actor{
    FontColor #73ae42
    BackgroundColor #73ae42
    BorderColor #73ae42
    Shadowing false
}
skinparam usecase {
    FontColor White 
    ArrowColor #5b9bd5
    BackgroundColor #5b9bd5
    BorderColor #5b9bd5
    Shadowing false
}
rectangle "Book store"{
    Customer -- (Find a book)
    Customer -- (add to cart)
    Customer -- (Checkout)
    (make invoice) -- Employee
    (payment) -- Employee
    Customer -- (payment)
    (Print slip) -- Employee
}
@enduml
```