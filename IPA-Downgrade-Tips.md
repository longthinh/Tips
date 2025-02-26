# Hướng dẫn hạ cấp ứng dụng iOS

## Sử dụng Fiddler Classic | IPADOWN

### Điều kiện bắt buộc

#### Đây là phương pháp hạ cấp thông thường cho nên:

- Ứng dụng phải còn tồn tại trên App Store
- Đã tải ứng dụng về Apple ID để có Lisence
- Phải có appVerId (sẽ hướng dẫn ở Bước 03)
- Sử dụng trên Windows

### Bắt đầu

#### Bước 1. Cài đặt và sử dụng Fiddler Classic

- Tải về [Fiddler Class](https://www.telerik.com/download/fiddler)
- Tải về [iTunes 12.6.5.3](https://secure-appldnld.apple.com/itunes12/091-87819-20180912-69177170-B085-11E8-B6AB-C1D03409AD2A6/iTunes64Setup.exe) đây là bản cuối cùng hỗ trợ tải tệp ứng dụng
- Công cụ giải nén WinRAR
- Sau khi tải về Fiddler Class và iTunes thì bấm cài đặt: Next > Next > cho đến khi cài đặt hoàn tất

#### Bước 2. Cài đặt chứng chỉ cho Fiddler Class

- Mở Fiddler Class và Nhấn "No" nếu có hỏi cập nhật và làm theo như ảnh (nếu thích cập nhật mà bị lỗi thì cứ cập nhật). Tùy!
  ![1](https://github.com/user-attachments/assets/23063c91-c5dd-4a98-940a-b1b5211c3af7)
- Chọn Tools > Options.. > chọn thẻ HTTPS
  ![2](https://github.com/user-attachments/assets/55241fce-3db4-441e-a626-266b348eb433)
- Nhấp chọn Decrypt HTTPS traffic > Chọn "No" nếu có hộp thoại hiện lên và nhấp chọn Actions > Export Root Certificate to Desktop
  ![3](https://github.com/user-attachments/assets/a99bfb55-700c-4b05-8461-261304b0caa5)
- Nhấp vào FiddlerRoot.cer trên Desktop để cài đặt và làm theo như hình và chọn Install Certificate...
  ![4](https://github.com/user-attachments/assets/e02e316a-8436-4b54-a768-3edac555340f)
  
  ![5](https://github.com/user-attachments/assets/d8306fca-2d11-49a4-a37a-0a6ca959783f)
  
  ![6](https://github.com/user-attachments/assets/71bc1e6b-aa18-4016-958f-27155dcce0ee)
- Chọn Trusted Root Certification Authorities và nhấn OK > Finish > Xong phần cài đặt Fiddler Classic và Certificate
  ![7](https://github.com/user-attachments/assets/335b529a-e00c-4df4-97c7-022a6725aa8a)

#### Bước 3. Lấy appVerId tương ứng với phiên bản của ứng dụng
- Nếu đã có trước appVerId thì sang luôn Bước 4
- Mở iTunes > Đăng nhập > Purchased > nhấp tải ứng dụng cần hạ cấp
- Ném tệp ipa của ứng dụng ra thư mục bất kỳ ngoài Desktop để giải nén
- Đổi định dạng .ipa thành .zip rồi giải nén
- Tìm và mở tệp iTunesMetadata.plist bằng Notepad hoặc bất cứ thứ gì có hỗ trợ
- Tìm đến đoạn mã như trong ảnh (phiên bản mới nhất là phiên bản nằm phía dưới)
![Visual Studio Code 2025-02-26 7_21_39 PM](https://github.com/user-attachments/assets/17b2d523-bfbe-4bea-8f50-8d3d1f127509)
- Động não và tư duy tính toán để đối chiếu phiên bản đó tương ứng với appVerId nào trong mảng trong hình và sao chép dãy số nguyên đó

#### Bước 4. Tải phiên bản cũ
- Sau khi đã có được appVerId thì có thể dùng [IPADOWN](https://ipadown.thuthuatjb.com/) và làm theo hướng dẫn trên Website để tải hoặc tiếp tục dùng Fiddler Classic để tải
- Mở Fiddler Classic lên nhập `bpu MZBuy` vào Textbox phía dưới và Enter để cản Request đi thẳng đến Server trước khi ta nhập vào appVerId
![Screenshot (4)](https://github.com/user-attachments/assets/366981ca-2ee4-4575-8469-5a2940d44e90)
- Mở iTunes và tìm đến ứng dụng cần hạ cấp và nhấp tải và nhìn sang Fiddler Classic nhấp đúp vào biểu tượng màu đỏ `p23-buy.itunes.app..`
![Progress Telerik Fiddler Classic 2025-02-26 7_33_47 PM](https://github.com/user-attachments/assets/26519bff-b214-4ee4-9099-7ae4b0860c08)
- Chọn TextView > dán appVerId vào > Run to Completion > iTunes sẽ tự tải phiên bản ứng dụng tương ứng với appVerId đã dán vào
- Sao lưu lại tệp ipa đó ở một nơi an toàn hoặc dùng 3uTools để cài luôn vào thiết bị

#### Lưu ý
- Tệp ipa tải về là chính chủ theo Apple ID có hiệu lực vĩnh viễn
- Đối với tệp ipa không có In-app có thể cài trực tiếp thông qua `itms-services`
- Đối với tệp ipa có In-app bắt buộc phải dùng 3uTools hoặc iMazing để cài thông qua PC để không bị lỗi load In-app

### Author
- [𝔏𝔬𝔫𝔤 𝔗𝔥𝔦𝔫𝔥](https://github.com/longthinh) | [𝙻𝚞𝚡𝚢𝚍𝚎𝚟](https://github.com/longthinh)
