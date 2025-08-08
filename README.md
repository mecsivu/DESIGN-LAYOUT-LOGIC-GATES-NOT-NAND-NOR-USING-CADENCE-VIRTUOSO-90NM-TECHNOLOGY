# DESIGN-LAYOUT-LOGIC-GATES-NOT-NAND-NOR-USING-CADENCE-VIRTUOSO-90NM-TECHNOLOGY
1.  Thiết kế cổng NOT
1.1. Lý thuyết
a.Ký hiệu và bản trạng thái
   <img width="880" height="352" alt="image" src="https://github.com/user-attachments/assets/a6c6ebcc-f2ed-4c35-ac72-325534b3b08e" />
b.Sơ đồ nguyên lý
   <img width="304" height="300" alt="image" src="https://github.com/user-attachments/assets/92033027-cebe-46b0-a947-68bf30655540" />
2. Simulation
   <img width="826" height="947" alt="image" src="https://github.com/user-attachments/assets/9252046b-052f-429a-86c7-d958f05d39aa" />
- Vì độ linh động của NMOS lớn hơn PMOS khoảng hai lần, nên khi thiết kế, khối PUN (Pull-Up Network) cần có tỷ lệ W/L gấp đôi tỷ lệ W/L của khối PDN (Pull Down Network). Điều này nhằm đảm bảo dòng ngõ ra cân bằng, giúp thời gian chuyển mạch của mạch là như nhau, từ đó làm cho mạch ổn định hơn, tăng độ chính xác, đồng thời hạn chế dòng ngắn mạch và giảm công suất tiêu tán.
- WpMOS = 2WnMOS 
<img width="761" height="178" alt="image" src="https://github.com/user-attachments/assets/67bf2876-fd54-4416-8812-2972c8dc763b" />
2.2 Đóng gói
<img width="699" height="469" alt="image" src="https://github.com/user-attachments/assets/4af67ad8-d61e-49b7-97c5-5915f8b4c8ce" />
3. Dạng sóng
