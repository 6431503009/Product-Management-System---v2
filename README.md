# ระบบจัดการสินค้า (Product Management System) ด้วย Node.js และ Express Version 2
Task Week 3 : Back-End Dev for Dev Init
Authors
assignment by @BorntoDev
implementation by @Chuntawat

เมื่อผู้ใช้ Run ระบบจัดการสินค้านี้ ด้วย Code
#npm run dev

ผู้ใช้จะสามารถเข้าไปอ่าน คู่มือการใช้งาน API ของระบบจัดการสินค้า ได้โดย display ผ่าน live server

![image](https://github.com/6431503009/Product-Management-System/assets/97873903/1aedc0b2-5f9c-43fa-b60f-c96740982de0)

ส่วนนี้จะเป็นหน้าตาของ ระบบสามารถ responce กับ Api end point ได้ (สามารถเลือกโหมดมืดกับสว่างได้) ใน version2 ได้สร้างปุ่มให้เพิ่มข้อมูล,เเก้ไข,ลบ

![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/b185f131-7764-4831-996a-df766dddd39e)


# RESTful API สำหรับจัดการสินค้า

RESTful API นี้ถูกสร้างขึ้นโดยใช้ Express.js สำหรับจัดการรายการสินค้า มีฟังก์ชันการทำงานดังนี้:

## รายการจุดสิ้นสุดการให้บริการ (Endpoints)

### 1. POST /products
- เพิ่มสินค้าใหม่
- ต้องกำหนดค่า `name`, `category`, `price` และ `stock` ซึ่งเป็นสตริง, สตริง, จำนวนเต็ม และจำนวนเต็มตามลำดับ
- `price` และ `stock` ต้องมีค่ามากกว่า 0

![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/e7251511-472a-4426-888a-178fce2bb4da)

![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/f0fb2e68-f640-4d2f-925d-2cb20e746b44)


### 2. POST /products/:id
- เพิ่มสินค้าใหม่ด้วยรหัสสินค้าที่กำหนด
- ต้องกำหนดค่า `name`, `category`, `price` และ `stock` เช่นเดียวกับ POST /products
- จะไม่สามารถเพิ่มสินค้าได้หากมีรหัสสินค้านั้นอยู่แล้ว

### 3. GET /products
- ดูรายการสินค้าทั้งหมด
![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/a03501fd-1962-40fb-9991-367ff4a3de1c)


### 4. PUT /products/:id
- แก้ไขข้อมูลสินค้า
- ต้องกำหนดค่า `name`, `category`, `price` และ `stock` ใหม่
- หากไม่พบสินค้าที่ต้องการแก้ไข จะได้รับข้อความ "ไม่พบสินค้าที่ต้องการ"
  ![image](https://github.com/6431503009/Product-Management-System/assets/97873903/548f9dec-bbcb-4d46-8f39-ed29e8dea95b)
  
  ![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/b43c14e2-cff4-4734-86b4-adda94c6ef4d)



### 5. DELETE /products/:id
- ลบสินค้าตามรหัสสินค้า
![image](https://github.com/6431503009/Product-Management-System/assets/97873903/fce12e0b-dd69-418d-80ff-c73713551a1f)
![image](https://github.com/6431503009/Product-Management-System/assets/97873903/df083f7a-9040-44c1-99a8-c7bc54dce787)
- สามารถลบสินค้าทั้งหมดได้ จะได้รับข้อความ "สินค้าทั้งหมดถูกลบแล้ว และได้รีไอดีสินค้าทั้งหมดใหม่"
![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/e4b4ed45-f00d-4753-b8f5-2268ef2ee113)
- หากไม่พบสินค้าที่ต้องการลบ จะได้รับข้อความ "ไม่พบสินค้าที่ต้องการ"
- ในกรณีถ้าลบข้ามเลขไอดีเช่น 123 เเล้วลบ ไอดี 2 เลขไอดี 3 ก็จะเป็น 2 เพิ่อให้เลขไอดีเรียงตาวมคิวได้
![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/2e3e2ee4-e5a9-411b-971f-72463c6e3da5)
![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/6faf50bf-8784-4832-ac74-c18098e09200)
![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/9f2bab48-47fd-422d-8232-54f8e4570f92)
![image](https://github.com/6431503009/Product-Management-System---v2/assets/97873903/0a891e89-0981-4431-adc1-1200f5f09b87)




## หมายเหตุ
- ข้อมูลสินค้าจะถูกจัดเก็บได้อัปเกรดมาในรูปแบบ SQL 
- มีการตรวจสอบค่าว่างเปล่า ประเภทข้อมูล และเงื่อนไขอื่นๆ ก่อนดำเนินการกับข้อมูล
