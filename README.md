# DESIGN-LAYOUT-LOGIC-GATES-NOT-NAND-NOR-USING-CADENCE-VIRTUOSO-90NM-TECHNOLOGY
# 1. Thiết kế cổng NOT

## 1.1 Lý thuyết

### a.Ký hiệu và bản trạng thái
   <img width="880" height="352" alt="image" src="https://github.com/user-attachments/assets/a6c6ebcc-f2ed-4c35-ac72-325534b3b08e" />
   
### 1.2 Sơ đồ nguyên lý (Transistor Level CMOS)
   <img width="304" height="300" alt="image" src="https://github.com/user-attachments/assets/92033027-cebe-46b0-a947-68bf30655540" />
   
## 1.3 Schematic 

   <img width="973" height="936" alt="image" src="https://github.com/user-attachments/assets/448efd98-1750-469e-bd65-cb820158c658" />
   
   <br>
   - Vì độ linh động của NMOS lớn hơn PMOS khoảng hai lần, nên khi thiết kế, khối PUN (Pull-Up Network) cần có tỷ lệ W/L gấp đôi tỷ lệ W/L của khối PDN (Pull Down Network). Điều này nhằm đảm bảo dòng ngõ ra cân bằng, giúp thời gian chuyển mạch của mạch là như nhau, từ đó làm cho mạch ổn định hơn, tăng độ chính xác, đồng thời hạn chế dòng ngắn mạch và giảm công suất tiêu tán.
   <br>
   - WpMOS = 2WnMOS
   <br>
   <br>
     
   <img width="761" height="178" alt="image" src="https://github.com/user-attachments/assets/67bf2876-fd54-4416-8812-2972c8dc763b" />
   
## 1.4 Đóng gói

   <img width="699" height="469" alt="image" src="https://github.com/user-attachments/assets/4af67ad8-d61e-49b7-97c5-5915f8b4c8ce" />
   
## 1.5 Dạng sóng

   <img width="947" height="467" alt="image" src="https://github.com/user-attachments/assets/5e66a0de-7940-4e78-b224-9b515e2ba9b9" />

 ##  1.6 Độ trễ lan truyền (Propagation Delay)
 
### a.  Độ trễ lan truyền cạnh xuống

<img width="636" height="498" alt="image" src="https://github.com/user-attachments/assets/33d0221f-5796-4c5e-89d2-22836daaf7c5" />

Giải thích:
 - Vin đi từ 1.2V xuống, thời gian trễ lan truyền cạnh xuống (ngõ ra) nên sẽ đo khoảng thời gian Vin=VDD/2 và Vout=VDD/2. 
- Sóng màu đỏ (IN) ở trên là mức điện áp xuống đo từ ngõ vào. 
- Sóng màu xanh (OUT) ở dưới là mức điện áp lên đo từ ngõ ra. 
- A(40.000050us;600mV) là VDD/2 của Vin. 
- B(40.000053us;600mV) là VDD/2 của Vout. 
- Thời gian độ trễ lan truyền cạnh xuống là :
	tpdf=3.134591ps
### b. Độ trễ lan truyền cạnh lên

<img width="636" height="374" alt="image" src="https://github.com/user-attachments/assets/00fa06e4-b9a6-4794-8225-4fed9ee81289" />

Giải thích:
 - Vin đi từ 1.2V xuống, thời gian trễ lan truyền cạnh lên (ngõ ra) nên sẽ đo khoảng thời gian Vin=VDD/2 và Vout=VDD/2. 
- Sóng màu đỏ (IN) ở trên là mức điện áp xuống đo từ ngõ vào. 
- Sóng màu xanh (OUT) ở dưới là mức điện áp lên đo từ ngõ ra. 
- A(10.00015us;600mV) là VDD/2 của Vin. 
- B(10.77605us;600mV) là VDD/2 của Vout. 
- Thời gian độ trễ lan truyền cạnh lên là :
	tpdr=10.78089ps 

### c.Kết luận
Tpd = (tpdf+tpdr)/2 = 6.9577ps

 ###  1.7 Thời gian chuyển mạch (Transition time )

  
### a. Thời gian chuyển mạch cạnh xuống

<img width="499" height="282" alt="image" src="https://github.com/user-attachments/assets/263c2585-938c-471f-a2fb-bc1059c9e906" />

  Để tính thời gian cạnh xuống, ta đo từ khoảng 90% VDD (1.08V) tới 10% VDD (120mV) đối với Output.
 -	Trên hình vẽ, điểm A đo 90% VDD có tọa độ (20.000038us ;1.08V)
 -	Điểm B đo 10% VDD có tọa độ (20.000064us, 120mV)
 -	Ta tính được thời gian cạnh xuống bằng: tf=25.8105ps.

### b. Thời gian chuyển mạch cạnh lên

<img width="547" height="449" alt="image" src="https://github.com/user-attachments/assets/ac74f1ea-f027-4276-a522-2d690ff85e21" />

  Để tính thời gian cạnh lên, ta đo từ khoảng 10% VDD (120mV) tới 90% VDD (1.08V) đối với Output.
 -	Trên hình vẽ, điểm A đo 10% VDD có tọa độ (10.00014514us ;120mV)
 -	Điểm B đo 90% VDD có tọa độ (10.00017333us, 1.08V)
 -	Ta tính được thời gian cạnh lên bằng: tr=28.1870085ps.
## 1.8 Công suất

<img width="354" height="247" alt="image" src="https://github.com/user-attachments/assets/f91d0215-5114-48f0-9370-600b709214e8" />

Công suất trung bình của 1 cổng NOT : Pavg=3.237uW.

## 1.9 Thiết kế Layout

<img width="760" height="1004" alt="image" src="https://github.com/user-attachments/assets/3f685658-3edc-4730-aaac-322a0e13a115" />

## 1.10 Kiểm tra DRC 

<img width="756" height="988" alt="image" src="https://github.com/user-attachments/assets/c1f4be63-4ea0-48b4-803e-2ad3d05afc71" />

## 1.11 Kiểm tra LVS

<img width="754" height="989" alt="image" src="https://github.com/user-attachments/assets/29eec93f-0ce1-4a8b-9964-7b59d3b9e4f1" />

<img width="753" height="986" alt="image" src="https://github.com/user-attachments/assets/9676e6ff-267e-4443-945b-aa9f0ee25f62" />

## 1.12 Kết luận:

Sau khi hai quá trình DRC và LVS đều thành công thì đảm bảo về cơ bản :
- Thiết kế layout đã chính xác về mặt vật lý và logic.
- Layout đã tuân thủ các quy tắc sản xuất và thể hiện chính xác sơ đồ nguyên lý.

# 2.Thiết kế cổng NAND

## 2.1 Lý thuyết

Ký hiệu và bản trạng thái

<img width="497" height="319" alt="image" src="https://github.com/user-attachments/assets/4d679d29-163d-4135-8a67-601b7cb95e9a" />

## 2.2 Sơ đồ nguyên lý (Transistor Level CMOS)

<img width="285" height="186" alt="image" src="https://github.com/user-attachments/assets/016c754b-1254-499c-ac1d-209cca4ae3b5" />

## 2.3 Schematic 

<img width="510" height="531" alt="image" src="https://github.com/user-attachments/assets/a784113f-1bfe-4322-be8f-1543a7c89a97" />

- Vì độ linh động của NMOS lớn hơn PMOS khoảng hai lần, nên khi thiết kế, khối PUN (Pull-Up Network) cần có tỷ lệ W/L gấp đôi tỷ lệ W/L của khối PDN (Pull Down Network). Điều này nhằm đảm bảo dòng ngõ ra cân bằng, giúp thời gian chuyển mạch của mạch là như nhau, từ đó làm cho mạch ổn định hơn, tăng độ chính xác, đồng thời hạn chế dòng ngắn mạch và giảm công suất tiêu tán.

- WpMOS = 2WnMOS

 <img width="715" height="226" alt="image" src="https://github.com/user-attachments/assets/b4666074-4ccf-45e2-b4d6-031a77a4b28b" />

## 2.4 Đóng gói

<img width="506" height="419" alt="image" src="https://github.com/user-attachments/assets/dcb47b55-2cd6-4f76-b5cf-d43806bd8a3e" />

## 2.5 Dạng sóng

<img width="788" height="392" alt="image" src="https://github.com/user-attachments/assets/952c04f3-bd08-47a6-a540-0dfa08ffb0b6" />

 ##  2.6 Độ trễ lan truyền (Propagation Delay)

### a.  Độ trễ lan truyền cạnh xuống
<img width="624" height="396" alt="image" src="https://github.com/user-attachments/assets/cc4a1d8c-4a84-4363-ad64-d18dc9d34369" />

Giải thích:
 - Vin đi từ 0-1.2V, thời gian trễ lan truyền cạnh xuống (ngõ ra) nên sẽ đo khoảng thời gian Vin=VDD/2 và Vout=VDD/2. 
- Sóng màu xanh (IN) ở trên là mức điện áp xuống đo từ ngõ vào. 
- Sóng màu tím (OUT) ở dưới là mức điện áp lên đo từ ngõ ra. 
- A(40.00005us ; 600mV) là VDD/2 của Vin. 
- B(40.000059us ; 600mV) là VDD/2 của Vout. 
- Thời gian độ trễ lan truyền cạnh xuống là :
            tpdf=9.70689ps

### b. Độ trễ lan truyền cạnh lên
<img width="624" height="342" alt="image" src="https://github.com/user-attachments/assets/6085bb0e-2a9f-4c91-a563-702fa018f629" />

Giải thích:
 - Vin đi từ 1.2V xuống, thời gian trễ lan truyền cạnh lên (ngõ ra) nên sẽ đo khoảng thời gian Vin=VDD/2 và Vout=VDD/2. 
- Sóng màu đỏ (IN) ở trên là mức điện áp xuống đo từ ngõ vào. 
- Sóng màu tím(OUT) ở dưới là mức điện áp lên đo từ ngõ ra. 
- A(10.00015us ; 600mV) là VDD/2 của Vin. 
- B(10.00017us ; 600mV) là VDD/2 của Vout. 
- Thời gian độ trễ lan truyền cạnh lên là :
            tpdr=25.10109ps

### c.Kết luận
Tpd = (tpdf+tpdr)/2 = 17.40399ps

 ##  2.7 Thời gian chuyển mạch (Transition time )
 
### a. Thời gian chuyển mạch cạnh xuống

<img width="609" height="323" alt="image" src="https://github.com/user-attachments/assets/cdef9c0c-09f4-4c20-8e74-83821d9e88d9" />

Để tính thời gian cạnh xuống, ta đo từ khoảng 90% VDD (1.08V) tới 10% VDD (120mV) đối với Output.
-	Trên hình vẽ, điểm A đo 90% VDD có tọa độ (40.0000489us;1.08V)
-	Điểm B đo 10% VDD có tọa độ (40.0000712us;120mV)
-	Ta tính được thời gian cạnh xuống bằng: tf=22.2985ps.

### b. Thời gian chuyển mạch cạnh lên
<img width="531" height="307" alt="image" src="https://github.com/user-attachments/assets/c98f49cf-540c-4b60-abc0-402fa83aaca2" />

Để tính thời gian cạnh lên, ta đo từ khoảng 10% VDD (120mV) tới 90% VDD (1.08V) đối với Output.
- Trên hình vẽ, điểm A đo 90% VDD có tọa độ (10.000188us ;1.08V)
- Điểm B đo 10% VDD có tọa độ (10.000161us ;120mV)
- Ta tính được thời gian cạnh lên bằng: tr=26.98969ps.

## 2.8 Công suất
<img width="329" height="210" alt="image" src="https://github.com/user-attachments/assets/441d375d-7b35-4639-983e-655fa172616d" />

Công suất trung bình của 1 cổng NAND : Pavg=41.48nW.

## 2.9 Thiết kế Layout

<img width="740" height="914" alt="image" src="https://github.com/user-attachments/assets/7cbb8624-6880-48da-812d-b6f761d2754d" />

## 2.10 Kiểm tra DRC 

<img width="740" height="913" alt="image" src="https://github.com/user-attachments/assets/16161886-0d42-4ee7-80e4-62ec6cef289c" />

## 2.11 Kiểm tra LVS

<img width="789" height="981" alt="image" src="https://github.com/user-attachments/assets/c0f869c6-653c-406d-a0c5-b0113342e64a" />

<img width="788" height="973" alt="image" src="https://github.com/user-attachments/assets/39c42329-d4b0-4bdc-a56c-f5fe0cc556aa" />

## 2.12 Kết luận:

Sau khi hai quá trình DRC và LVS đều thành công thì đảm bảo về cơ bản :
- Thiết kế layout đã chính xác về mặt vật lý và logic.
- Layout đã tuân thủ các quy tắc sản xuất và thể hiện chính xác sơ đồ nguyên lý.

# 3.Thiết kế cổng NOR

## 3.1 Lý thuyết

Ký hiệu và bản trạng thái

<img width="513" height="443" alt="image" src="https://github.com/user-attachments/assets/d04c1a0a-6655-4a48-b608-09f968ad8d7c" />

## 3.2 Sơ đồ nguyên lý (Transistor Level CMOS)

<img width="389" height="343" alt="image" src="https://github.com/user-attachments/assets/0f43305d-942e-475b-806d-08d49ac82894" />

## 3.3 Schematic 

<img width="558" height="548" alt="image" src="https://github.com/user-attachments/assets/da3556be-3f9c-47aa-b0b3-c75e7c1056bb" />

- Vì độ linh động của NMOS lớn hơn PMOS khoảng hai lần, nên khi thiết kế, khối PUN (Pull-Up Network) cần có tỷ lệ W/L gấp đôi tỷ lệ W/L của khối PDN (Pull Down Network). Điều này nhằm đảm bảo dòng ngõ ra cân bằng, giúp thời gian chuyển mạch của mạch là như nhau, từ đó làm cho mạch ổn định hơn, tăng độ chính xác, đồng thời hạn chế dòng ngắn mạch và giảm công suất tiêu tán.
  
- WpMOS = 2WnMOS

<img width="765" height="258" alt="image" src="https://github.com/user-attachments/assets/4c593b7a-7d5a-4ffa-9027-ce2acbf5013c" />

  ## 3.4 Đóng gói

  <img width="657" height="462" alt="image" src="https://github.com/user-attachments/assets/8f62659d-4e59-44fe-ad46-f3fe093f1f0b" />

## 3.5 Dạng sóng

<img width="860" height="438" alt="image" src="https://github.com/user-attachments/assets/a2646b70-eb3d-4b3f-88b7-9c0daa817fcb" />

 ##  3.6 Độ trễ lan truyền (Propagation Delay)

 
### a.  Độ trễ lan truyền cạnh xuống

<img width="563" height="360" alt="image" src="https://github.com/user-attachments/assets/17e5eaa8-ac40-4b25-8d8a-2b3e2bd5cfa5" />

Giải thích:
 - Vin đi từ 0-1.2V, thời gian trễ lan truyền cạnh xuống (ngõ ra) nên sẽ đo khoảng thời gian Vin=VDD/2 và Vout=VDD/2. 
- Sóng màu xanh (IN) ở trên là mức điện áp xuống đo từ ngõ vào. 
- Sóng màu tím (OUT) ở dưới là mức điện áp lên đo từ ngõ ra. 
- A(40.00005us ; 600mV) là VDD/2 của Vin. 
- B(40.00004us ; 600mV) là VDD/2 của Vout. 
- Thời gian độ trễ lan truyền cạnh xuống là :
            tpdf=5.4285ps.

### b. Độ trễ lan truyền cạnh lên

<img width="624" height="454" alt="image" src="https://github.com/user-attachments/assets/dbccf9eb-e6fe-40bb-b81d-987ffc0c1a7c" />

Giải thích:
 - Vin đi từ 1.2V xuống, thời gian trễ lan truyền cạnh lên (ngõ ra) nên sẽ đo khoảng thời gian Vin=VDD/2 và Vout=VDD/2. 
- Sóng màu đỏ và xanh (IN) ở trên là mức điện áp xuống đo từ ngõ vào. 
- Sóng màu tím(OUT) ở dưới là mức điện áp lên đo từ ngõ ra. 
- A(30.00015us ; 600mV) là VDD/2 của Vin. 
- B(30.00016us ; 600mV) là VDD/2 của Vout. 
- Thời gian độ trễ lan truyền cạnh lên là :
            tpdr=18.614434ps.

### c.Kết luận
Tpd = (tpdf+tpdr)/2 = 12.021467ps

 ##  3.7 Thời gian chuyển mạch (Transition time )

 ### a. Thời gian chuyển mạch cạnh xuống
 
 <img width="609" height="313" alt="image" src="https://github.com/user-attachments/assets/0efb4d7f-7a7b-4a3f-b375-48fa07168eca" />

Để tính thời gian cạnh xuống, ta đo từ khoảng 90% VDD (1.08V) tới 10% VDD (120mV) đối với Output.
-	Trên hình vẽ, điểm A đo 90% VDD có tọa độ (40.000032us;1.08V)
-	Điểm B đo 10% VDD có tọa độ (40.0000532us;120mV)
-	Ta tính được thời gian cạnh xuống bằng: tf=21.41127ps.

### b. Thời gian chuyển mạch cạnh lên

<img width="504" height="295" alt="image" src="https://github.com/user-attachments/assets/9e8d6ea4-b3c3-4617-a071-d5ebdc9c8b44" />

Để tính thời gian cạnh lên, ta đo từ khoảng 10% VDD (120mV) tới 90% VDD (1.08V) đối với Output.
-	Trên hình vẽ, điểm A đo 90% VDD có tọa độ (30.000185us ;1.08V)
-	Điểm B đo 10% VDD có tọa độ (30.000156 ;120mV)
-	Ta tính được thời gian cạnh lên bằng: 28.5249ps.

## 3.8 Công suất

<img width="347" height="217" alt="image" src="https://github.com/user-attachments/assets/be0f58c5-7abd-4bee-be81-5147220eba74" />

Công suất trung bình của 1 cổng NOR : Pavg=26.55nW.

## 3.9 Thiết kế Layout

<img width="761" height="994" alt="image" src="https://github.com/user-attachments/assets/5a7c457a-cfb3-44d4-a823-570feac83b8a" />

## 3.10 Kiểm tra DRC 

<img width="764" height="998" alt="image" src="https://github.com/user-attachments/assets/62909114-ec17-4ad6-8f10-7e5ccc125cb9" />


## 3.11 Kiểm tra LVS

<img width="754" height="994" alt="image" src="https://github.com/user-attachments/assets/9f562a67-8cd4-4a53-8336-87b6926a619b" />

<img width="755" height="994" alt="image" src="https://github.com/user-attachments/assets/247e8b8f-6e4c-4c7b-8290-ceae27507abe" />

## 3.12 Kết luận:

Sau khi hai quá trình DRC và LVS đều thành công thì đảm bảo về cơ bản :
- Thiết kế layout đã chính xác về mặt vật lý và logic.
- Layout đã tuân thủ các quy tắc sản xuất và thể hiện chính xác sơ đồ nguyên lý.
