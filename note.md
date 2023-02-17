# du an hoc truc tuyen
## danh cho ng dung
- Hiển thị danh sách khoas học
- hiển thị TT chi tiết khóa học
- xem video
- download tài lieu
- học thử bài giảng
- ĐK/ đăng nhập
- trang TK
- mua khóa 
- giỏ hang
- hiển thị ds tt
- hiển thị cchi tiết tin tức
## dành cho quản trị viên

- QL danh mục
- QL học viên
- QL khóa học
- QL giảng viên
- QL bài giảng
- QL danh mục TT
- kích hoạt khóa cho học viên
- QL file tài liệu
- QL video
- QL don hang
- QL ng dùng (QL hệ thống)
- phân quyền quản trị hệ thống
- báo cáo ,thống kê.

## api

-xây dựng API hoàn chỉnh
## phân tích data base

1. table categories => ql danh mục
-id => int
-name => varchar(200) 
-slug => varchar(200) dùng để link đg dẫn tĩnh 
-parent_id => int phân cấp cha con
-created_at =>timestamp
-update_at => timestamp

2. table courses => ql khoas hoc
-id =>int
-name =>varchar(255)
-slug=>varchar (255)
-detail ->text  = thông tin
-teacher_id => int
-thumbbnail => varchar(255)   link anh
-price => float
-sale_price => float  
-code => varchar()   ma khoa hoc
-duration_lession =>float = trang thai tai lieu di kem , thogn tin them
-is_doccument => tinyint  = tai lieu
-support => text = lien he ho tro
-status => tiny = khóa học ra mắt chưa
-created_at =>timestamp
-update_at => timestamp

3. Table lessions =>QL bài giảng
-id =>int
-name => varchar(255)
-video_id => int
-document_id => int
-parent_id => int  = phan ccap bai giang
-is_trial => tinyint  = cho phep hoc thu
-views => int  =luot xem
-postition => int = sap xep
-duration => float  = thời lượng bài giảng
- desciption => float = thog tin bai giang
-created_at =>timestamp
-update_at => timestamp

4. Table categories_courses => trung gian LK cdanh mục khóa học
-id =>int
-category_id => int
-course_id => int
- created_at =>timestamp
- update_at => timestamp

5. table teacher => giang vien
- id => int
- name => varchar(255)
- slug => varchar(255) url giang vien
- description =>text  thong tin giang vien
- exp => float
- image => varchar(255)
- created_at =>timestamp
- update_at => 

6. video => qL video
- id =>int
- name => varchar(255)
- url => varchar(255)
- created_at =>timestamp
- update_at => timestamp

7. table documet =>ql tai lieu bai giang
- id => int 
- name => varchar(255)
- url => varchar(255) upload url driver
- size => float = dung lg tai lieu
- created_at =>timestamp
- update_at => timestamp

8. table categories_post => ql danh muc TT
- id => int
- name => varchar(255)
- slug => varchar(255)
- parent_id => int
- created_at =>timestamp
- update_at => timestamp

9. table posts => ql tin tuc

- id => int
- title => varchar(255)
- slug => varchar(255)
- content => text              
- exceprt => text 
- thumbnail => varchar(255)
- created_at =>timestamp
- update_at => timestamp

10. table students => ql hoc vien

- id => int
- name => varchar(255)
- email => varchar(100)
- password => varchar(100)
- phone => varchar(20)
- address => varchar(200)
- status => tinyint(1)
- created_at =>timestamp
- update_at => timestamp

11. table student_course => trung gian hoc vien va khoa hoc

- id => int
- course_id => int
- students_id => int
- created_at =>timestamp
- update_at => timestamp

12. table orders => ql ddown hang dang ky cua hoc vien

- id => int
- student_id => int
- total => float     tong tien
- status => tinyint(1)
- created_at =>timestamp
- update_at => timestamp

13. table orders_detail => chi tiet don hang

- id => int
- order_id => int
- course_id => int
- price => float
- created_at =>timestamp
- update_at => timestamp

14. table order_status => ql tt don hang

- id => int
- name => varchar(255)
- created_at =>timestamp
- update_at => timestamp

//phan quyen
15. table users => quan tri he thong

- id => int
- name
- email
- password
- group_id

16. table group => qt nhom ng dung

id 
name
- permissions => text     chua chuoi json de phan quyen
- created_at =>timestamp
- update_at => timestamp

17. table modules => danh sacch cac module trong tran quan tri

id
name
- title => varchar(200)
- role => text      chua chuoi json bao gom hanh dong quyen 

18. table options => ql cac thiet lap
id
name
- value => text