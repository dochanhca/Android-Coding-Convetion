# Android-Coding-Convetion

## 1. Quy tắc đặt tên
### 1.1. Đặt tên file java
- Sử dụng nguyên tắc [Camel Case](http://en.wikipedia.org/wiki/CamelCase). Tức là viết hoa ký tự đầu tiên. Ví dụ: *TaskNetworkBase.java*
- Các ***Activity, Fragment, Dialog, View, Adapter...*** đều là các file java và được đặt theo nguyên tắc trên. Ngoài ra chúng phải được đặt với tiền tố tương ứng như: *ActivityLogin, FragmentNavigation, DialogConfirm...*

**[⬆ back to top](#table-of-contents)**
### 1.2 Đặt tên biến trong java
* Đặt tên biến phải có nghĩa, không nên viết tắt. 
* Hạn chế sử dụng public field. Nếu dùng phải bắt đầu bằng "public".
* Hằng số Public static final : dùng ALL_CAPS_WITH_UNDERSCORES.
```java
	public class MyClass {
    		public static final int SOME_CONSTANT = 42;
    		public int publicField;
    		private static MyClass sSingleton;
    		private int mPrivate;
    		protected int mProtected;
	}
```
* Với các biến là các view trong android thì phải có tiền tố đi trước tương ứng theo nguyên tắc:
   - Button - btn
   - EditText - edt
   - TextView - txt
   - Checkbox - chk
   - RadioButton - rb
   - ToggleButton - tb
   - Spinner - spn
   - Menu - menu
   - ListView - lv
   - GalleryView - gv
   - LinearLayout -ll
   - RelativeLayout - rl

**[⬆ back to top](#table-of-contents)**
### 1.3 Đặt tên method trong java
- Ký tự đầu tiên viết thường, các ký tự đầu tiên của các từ tiếp theo thì viết hoa.
- Tên method phải là động từ và rõ ràng, phản ánh đúng công việc của nó.
- Hạn chế viết tắt.

***Correct:***
```java
	public void calRadiusOfCircle(){

	}
```
***Incorrect:***
```java
	public void calRC(){

	}
```

**[⬆ back to top](#table-of-contents)**
### 1.4 Đặt tên xml file
_ Sử dụng nguyên tắc [Snake Case](https://en.wikipedia.org/wiki/Snake_case). Tức là viết thường toàn bộ, các từ cách nhau bởi ký tự _. Ví dụ: color_gray.
- Với các ***resources file*** phải đặt tên giống như mặc định của android. Ví dụ: *colors.xml, dimen.xml, strings.xml, arrays.xml...*.
- Với các xml resource của ***activity, fragment***... phải đặt với tiền tố tương ứng là *activity, fragment*... Ví dụ: *activity_home, fragment_comment...*.

**[⬆ back to top](#table-of-contents)**
### 1.5 Đặt tên xml id
- Tất cả đều phải viết thường và được ngăn cách bởi ký tự _ với các tên gồm nhiều từ.
- Đối với các view, việc đặt tên phải gồm tiền tố tương ứng theo nguyên tắc như trong [1.2] (#12-dat-ten-bien-trong-java). Ví dụ: *btnLogin, txtComment...*

**[⬆ back to top](#table-of-contents)**
### 1.6 Đặt tên xml resource name:
Tất cả đều phải viết thường và được ngăn cách bởi ký tự _ với các tên gồm nhiều từ.

**Với Image Resources**
- Đặt theo nguyên tắc ***group_type_name_state***
- Với ***background*** thì bắt đầu với tiền tố bg : *bg_button_post_comment_normal.*
- Với các ***icon*** thì bắt đầu với tiền tố ic: *ic_button_post_comment.*
_ Với các ***image*** thì bắt đầu với tiền tố img: *img_girl_xinh*

**Với Dimen Resources**
- Đặt theo nguyên tắc ***property_default_group_type_name*** . Với ***default***: có giá trị mặc định là *default*, nếu ko thì dùng *large, small*... ***Name***: chỉ dùng khi thực sự cần thiết.
- Ví dụ: *padding_default, margin_small_textview, height_default_action_bar_button*.

**Với String Resources**
- Đặt theo nguyên tắc ***group _name_state***.
- Ví dụ: *notif_like_success, title_setting_avatar, confirm_logout*.

**Với Color Resources**
- Nếu màu là phổ biến thì có thể đặt theo tên của màu. Ví dụ *white.* 
- Còn lại đặt theo nguyên tắc: ***group_type_name_state*** .
- Ví dụ: *activity_home_button_profile*.

**[⬆ back to top](#table-of-contents)**
### 1.7 Đặt tên method trong Android Test
- Ký tự đầu tiên viết thường, các ký tự đầu tiên của các từ tiếp theo thì viết hoa.
- Sử dụng dấu _ để ngăn cách giữa tên method test(thường mô tả phần tử được test) và case test.
- Ví dụ: testEditText_canBeTypedInto, testValidation_resultIsIncorrect …

**[⬆ back to top](#table-of-contents)**
## 2. Class
### 2.1 Sử dụng adapter và item
- Các Adapter chỉ được sử dụng để fill data vào listivew, và làm cầu nối giữa listview và activity, fragment. Không được sử dụng adapter để tính toán hay gửi request, lưu dữ liệu... 
- Nếu cần một list các Item thì tạo lớp cùng tên nhưng có thêm ký tự s, chứa một list các item. Ví dụ : *ItemUsers và ItemUser*. ItemUsers sẽ chứa một list các ItemUser.

**[⬆ back to top](#table-of-contents)**
### 2.2 Khai báo và sử dụng các hằng số
- Việc giao tiếp giữa các class, lưu trữ dữ liệu hay sử dụng các hằng phải được khai báo ***biến hằng*** trong class (*public static final*) chứ không được ***hard code***.
- Việc sử dụng các string để hiển thị thông báo đến người dùng phải được dùng qua giá trị được khai báo trong file ***strings.xml*** chứ không được ***hard code***.

**Correct:**

```java
	public class ActivityMain extends Activity{
	
		public static final String ITEM_USER = "ITEM USER";
		private void setResult(){
			Intent intent = new Intent();
			intent.putExtra(ITEM_USER, mItemPrefecture);
			setResult(RESULT_OK, intent);
		}

		private void notifyUpdateSuccessful(){
		        Toast.makeText(this, R.string.notif_update_successful, Toast.LENGTH_SHORT).show();
		}
		
	}
```

**Incorrect:**

```java
	public class ActivityMain extends Activity{
	
		private void setResult(){
			Intent intent = new Intent();
			intent.putExtra("ITEM USER", mItemPrefecture);
			setResult(RESULT_OK, intent);
		}
		private void notifyUpdateSuccessful(){
		        Toast.makeText(this, "Update Successful", Toast.LENGTH_SHORT).show();
		}
		
	}
```

**[⬆ back to top](#table-of-contents)**
### 2.3 Cách sắp xếp các thành phần trong một class
- Các properites được đặt lên trên cùng của class sau đó đến các constructor rồi mới đến các method.

- Sắp xếp các hàm chính (main) xử lý luồng lên đầu, các hàm càng chi tiết, càng ít quan trọng  bên dưới. Các hàm là override nên để trên các hàm chức năng và bên dưới các hàm xử lý luồng.

- Các biến có liên quan đến nhau nên đặt cạnh nhau. Các đoạn code có liên quan đến nhau( xử lý một nhóm việc liên quan) nên đặt liền nhau.  Mỗi đoạn này nên được tách nhau ra bằng một dòng trống.

**[⬆ back to top](#table-of-contents)**
## 3. Method
- Cấu trúc và thủ tục của hàm phải rõ ràng.  Định nghĩa, khai báo các properties ở đầu hàm, xong mới đến xử lý. 

- Mỗi method ngắn và chỉ nên làm một việc duy nhất. Để làm được như thế nên nghĩ làm cách nào để chia method thành những phần hành động nhỏ hơn.

- Mỗi dòng code nên  nhỏ hơn **100 ký tự**.

**[⬆ back to top](#table-of-contents)**
## 4.  Good Practices
### 4.1. Tránh sử dụng nhiều lệnh return
Việc sử dụng multiple return khiến việc debug khó và mất thời gian hơn.

**Correct:**

```java
 public class StringUtils {

 	public static boolean isEmpty(String string) {
 		return string == null || "".equals(string.trim());
 	}

 }

or

public class StringUtils {

 	public static boolean isEmpty(String string) {
 		boolean empty = false;
 		if (string == null) {
 			empty = true;
 		} else if ("".equals(string.trim())) {
 			empty = true;
 		}
 		return empty;
 	}

 }
```

**Incorrect:**

```java
public class StringUtils {

	public static boolean isEmpty(String string) {
 		if (string == null) {
 			return true;
 		} else if ("".equals(string.trim())) {
 			return true;
 		}
 		return false;
 	}

}
```

**[⬆ back to top](#table-of-contents)**
### 4.2.  So sánh các biến boolean

**Correct:**

```java
	!active
```

**Incorrect:**

```java
	active == false
```

**[⬆ back to top](#table-of-contents)**
### 4.3.  Vòng lặp for và for-each
Khi không quan tâm đến index trong vòng lặp thì ưu tiên sử dụng for-each sẽ khiến code dễ đọc và theo dõi hơn.

**Correct:**

```java
	for (String name: names) {
		doSomething(name);
	}
```

**Incorrect:**

```java
	for (int i = 0; i < names.length; i++) {
		doSomething(names[i]);
	}   
```

**[⬆ back to top](#table-of-contents)**
### 4.4. Câu lệnh if có một lệnh thực thi

**Correct:**

```java
	if (age > 18){
		doAction();
	}
```

**Correct:**

```java
	if (age > 18)   doAction();
```

**Incorrect:**

```java
	if (age > 18)
		doAction();
```

**[⬆ back to top](#table-of-contents)**
### 4.5.  Exceptions
- Không được bỏ qua Exceptions.
- Không được catch generic Exceptions.
- Không sử dụng finaly

**Correct:**
```java
	/** Set port. If value is not a valid number, 80 is substituted. */

	void setServerPort(String value) {
    		try {
        		serverPort = Integer.parseInt(value);
    		} catch (NumberFormatException e) {
        		serverPort = 80;  // default port for server 
    		}
	}

```
**Correct:**

```java
	void setServerPort(String value) throws ConfigurationException {
    		try {
        		serverPort = Integer.parseInt(value);
    		} catch (NumberFormatException e) {
        		throw new ConfigurationException("Port " + value + " is not valid.");
    		}
	}
```

**Incorrect:**

```java
	try {
	    someComplicatedIOFunction();        // may throw IOException 
	    someComplicatedParsingFunction();   // may throw ParsingException 
	    someComplicatedSecurityFunction();  // may throw SecurityException 
	    // phew, made it all the way 
	} catch (Exception e) {                 // I'll just catch all exceptions 
	    handleError();                      // with one generic handler!
	}
```

**Incorrect:**

```java
	void setServerPort(String value) {
	    try {
	        serverPort = Integer.parseInt(value);
	    } catch (NumberFormatException e) { }
	}
```

**[⬆ back to top](#table-of-contents)**
### 4.6.  Sử dụng Java Annotations mặc định
Sử dụng các Annotations mặc định của android như : *@Deprecated, @Override, @SuppressWarnings...*
```java
	// TODO: The third-party class com.third.useful.Utility.rotate() needs generics 
	@SuppressWarnings("generic-cast")
	List<String> blix = Utility.rotate(blax);
```
**[⬆ back to top](#table-of-contents)**
### 4.7.  Comment
Hạn chế sử dụng comment dòng code mà sử dụng các comment mô tả trên đầu các method, class, biến theo chuẩn của java như sau:

**Correct:**

```java
	/**
	* Returns a user object that can be stored in the data store. 
	* The name argument must be alphanumeric. 
	* <p>
	* This method always creates a new user, whether or not a user 
	* with the same name already exists. 
	*
	* @param  name the name given to a new user
	* @return      the newly created user
	* @see         OtherClassOfInterest
	*/
	public User createUser(String name) {
		User user = new User();
		user.setName(name);
		return user;
	}
```

**Incorrect:**
```java
 	// creates a user
	public User createUser(String name) {
 		User user = new User(); // a new user is always created
 		user.setName(name);
 		return user;
	}
