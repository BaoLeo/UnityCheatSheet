# Unity_Cheat_Sheet_Tieng_Viet
Bản Unity cheat sheet phiên dịch cho cộng đồng người Việt từ Naomi Le. Cảm ơn các bạn vì đã quan tâm.

# Unity_Cheat_Sheet
## Mục lục
- [Cơ bản](#cơ-bản)
  - [Phím tắt Unity](#phím-tắt-unity)
  - [MonoBehaviour](#monobehaviour)
  - [Sự kiện vật lý (Physics Events)](#sự-kiện-vật-lý)
  - [Serializing](#serializing)
  - [Khởi tạo](#khởi-tạo)
  - [Tìm Đối Tượng Trong Game](#tìm-đối-tượng-trong-game)
  - [Hủy Đối Tượng Trò Chơi](#hủy-đối-tượng-trò-chơi)
  - [Các Thành Phần (Components)](#các-thành-phần)
  - [Hằng Số (Constants)](#hằng-số)
  - [Vectors](#vectors)
  - [Quaternion](#quaternion)
  - [Góc Euler](#góc-euler)
  - [Giữ Tỉ Lệ Màn Hình](#giữ-tỉ-lệ-màn-hình)
  - [Custom Unity Events](#Sự-Kiện-Tùy-Chỉnh-Trong-Unity)
- [Di Chuyển & Xoay](#di-chuyển--xoay)
  - [Di Chuyển Đối Tượng](#di-chuyển-đối-tượng)
    - [Transform.Translate()](#transformtranslate)
    - [Vector3.MoveTowards()](#vector3movetowards)
    - [Vector3.Lerp()](#vector3lerp)
    - [Vector3.SmoothDamp()](#vector3smoothdamp)
  - [Xoay Đối Tượng](#xoay-đối-tượng)
    - [Transform.rotation](#transformrotation)
    - [Transform.eulerAngles](#transformeulerangles)
    - [Transform.Rotate()](#transformrotate)
    - [Transform.RotateAround()](#transformrotatearound)
    - [Transform.LookAt()](#transformlookat)
    - [Quaternion.LookRotation()](#quaternionlookrotation)
    - [Quaternion.FromToRotation()](#quaternionfromtorotation)
    - [Quaternion.ToAngleAxis()](#quaterniontoangleaxis)
  - [Time](#time)
  - [Rendering materials](#rendering-materials)
  - [Lighting](#lighting)
  - [Coroutine](#coroutine)
  - [Physics](#physics)
    - [Raycast](#raycast)
    - [Ignore Collision](#ignorecollision)
- [Input](#input)
  - [Bàn Phím](#bàn-phím)
  - [Chuột](#chuột)
  - [Chạm](#chạm)
- [Giao Diện Người Dùng (UI)](#giao-diện-người-dùng-ui)
  - [Nút (Button)](#nút-button)
  - [Thanh Trượt (Slider)](#thanh-trượt-slider)
- [Âm Thanh](#âm-thanh)
  - [Chơi Âm Thanh Cơ Bản](#chơi-âm-thanh-cơ-bản)
- [Mô Hình Thiết Kế](#mô-hình-thiết-kế)
  - [Singleton](#singleton)
  - [Factory Pattern](#factory-pattern)
  - [Observer Pattern](#observer-pattern)
  - [Command Pattern](#command-pattern)
  - [State Pattern](#state-pattern)
- [Các Ứng Dụng Thực Tế](#các-ứng-dụng-thực-tế)
- [Practical Use Cases](#practical-use-cases)
  - [Check if object is on the ground](#check-if-object-is-on-the-ground)
  - [Get the transform of a Body Bone](#get-the-transform-of-a-body-bone)
  - [Make object look at the camera](#make-object-look-at-the-camera)
  - [Load next scene](#load-next-scene)
-[Save Data](#save-data)
  - [PlayerPrefs](#playerPrefs)
  - [ScriptableObject](#scriptableobject)
  - [JSON](#json)
  - [Binary](#binary)
  - [Database (SQLite)](#database-sqlite)
  - [Lưu Scene và GameObject](#lưu-scene-và-gameObject)
- [Refernces](#refernces)

 ## Cơ Bản

### Phím tắt Unity
  
  | Hành động                         | Phím tắt                                             |
| ---------------------------------- | ---------------------------------------------------- |
| Công cụ Xem (View Tool            |Q                                                        |
| Công cụ Di Chuyển (Move Tool)     |W                                                        |
| Công cụ Xoay (Rotate Tool)        |E                                                        |
| Công cụ Thay Đổi Kích Thước (Scale Tool)      |R                                                        |
| Công cụ Hình Chữ Nhật (Rect Tool)            |T                                                        |
| Công cụ Biến Đổi (Transform Tool)                 |Y                                                        |
| Đối Tượng Trò Chơi Mới (New Game Object)         |Windows: CTRL + SHIFT + N <br> Mac: CMD + SHIFT + N      |
| Đối Tượng Con Mới (New Child Game Object)                |ALT + SHIFT + N                                          |
| Nhân Bản (Duplicate)               |Windows: CTRL + D <br> Mac: CMD +D                       |              
| Chuyển đổi Kích thước cửa sổ (Toggle Window Size)      |SHIFT + SPACE                                            |
| Chơi/Tạm Dừng (Play/Pause)        |Windows: CTRL + P <br> Mac: CMD + P                      |                            
| Tập Trung Đối Tượng Trò Chơi (Focus Game Object)      |F                                                        |
### Visual Studio Code

  | Hành động                         | Phím tắt                                             |
| ---------------------------------- | ---------------------------------------------------- |
| Command Palette                  | Windows: CTRL + SHIFT + P Mac: CMD + SHIFT + P            |
| Quick File Open                   | Windows: CTRL + P Mac: CMD + P                           |
| Toggle Sidebar                    | Windows: CTRL + B Mac: CMD + B                           |
| Multi-Select Cursor               | Windows: CTRL + D Mac: CMD + D                           |
| Copy Line                         | Windows: SHIFT + ALT + UP or SHIFT + ALT + DOWN Mac: OPT + SHIFT + UP or OPT + SHIFT + DOWN |
| Comment Code Block                | Windows: SHIFT + ALT + A (Multi-line comment), CTRL + K + C (Single-line comment) Mac: SHIFT + OPT + A |
| Show All Symbols                  | Windows: CTRL + T Mac: CMD + T                           |
| Trigger suggestion and parameter hints | Windows: Ctrl + Space, Ctrl + Shift + Space Mac: CMD + Space, CMD + Shift + Space |
| Show References                   | Windows: Shift + F12 Mac: Shift + F12                    |
| Global Find                       | Windows: CTRL + SHIFT + F Mac: CMD + SHIFT + F            |

### [MonoBehaviour](https://docs.unity3d.com/ScriptReference/MonoBehaviour.html)
[Đồ thị vòng Lifecycle của MonoBehaviour](https://docs.unity3d.com/uploads/Main/monobehaviour_flowchart.svg)

Tất cả các thành phần được thừa kế từ lớp MonoBehaviour thực hiện một loạt các hàm sự kiện theo một thứ tự xác định. Các hàm này bao gồm:
```csharp
Awake(): Được gọi sau khi một đối tượng trò chơi được khởi tạo.
OnEnable(): Được gọi khi một đối tượng trò chơi được kích hoạt.
Start(): Được gọi trước khi khung hình đầu tiên được cập nhật.
Update(): Gọi mỗi khung hình.
LateUpdate(): Được gọi mỗi khung hình sau khi hàm Update().
OnBecameVisible(): Được gọi khi đối tượng trò chơi hiện tại trở nên hiển thị thông qua bất kỳ camera nào.
OnBecameInvisible(): Được gọi khi đối tượng trò chơi hiện tại không còn hiển thị qua bất kỳ camera nào.
OnDrawGizmos(): Được gọi để vẽ gizmos trong cửa sổ scene.
OnGUI(): Được gọi nhiều lần cho các sự kiện GUI.
OnApplicationPause(): Được gọi khi trò chơi tạm dừng thông qua Unity editor.
OnDisable(): Thực thi khi đối tượng trò chơi bị tắt.
OnDestroy(): Được kích hoạt khi đối tượng trò chơi bị hủy.
```
Có một hàm vòng đời được gọi là `FixedUpdate`, được kích hoạt một số lần cố định mỗi giây. Bạn có thể cấu hình tần suất trong `Edit ▸ Project Settings ▸ Time ▸ Fixed Timestep`.

## Sự kiện vật lý
Nếu bạn thêm một thành phần collider vào một đối tượng trong game, bạn có thể phát hiện sự kiện va chạm từ các thành phần của bạn bằng cách định nghĩa một bộ phận cụ thể của các phương thức. Các phương thức sau chỉ được gọi khi bạn có một Collider hoặc Rigid Body component trên cả hai đối tượng trong game.
- OnCollisionEnter - Phương thức này được gọi một lần khi một đối tượng khác va chạm với đối tượng game hiện tại.
- OnCollisionStay - Phương thức này được gọi trong mỗi khung hình khi một đối tượng khác va chạm với đối tượng game hiện tại.
- OnCollisionExit - Phương thức này được gọi một lần khi một đối tượng rời khỏi vùng va chạm của đối tượng hiện tại.

```csharp
private void OnCollisionEnter(Collision hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnCollisionStay(Collision hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnCollisionExit(Collision hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
```
Các hàm sau chỉ được gọi khi tùy chọn "On Trigger" được bật từ thành phần collider tương ứng.
-OnTriggerEnter - Hàm này được gọi khi một đối tượng khác va chạm với đối tượng game hiện tại.
-OnTriggerStay - Hàm này được gọi trong mỗi khung hình khi một đối tượng khác va chạm với đối tượng game hiện tại.
-OnTriggerExit - Hàm này được gọi một lần khi một đối tượng rời khỏi vùng va chạm của đối tượng hiện tại.
```csharp
private void OnTriggerEnter(Collider hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnTriggerStay(Collider hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnTriggerExit(Collider hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
```
Cuối cùng, có các hàm tương ứng cho các collider 2D. Các hàm này chia sẻ cùng tên với các hàm 3D, nhưng có từ "2D" được thêm vào cuối. Tương tự, kiểu tham số cũng giống nhau, nhưng thay vì Collision, ta có Collision2D.
- OnCollisionEnter2D
- OnCollisionStay2D
- OnCollisionExit2D
- OnTriggerEnter2D
- OnTriggerStay2D
- OnTriggerExit2D
```csharp
private void OnCollisionEnter2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnCollisionStay2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnCollisionExit2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
private void OnTriggerEnter2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnTriggerStay2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnTriggerExit2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
```

### Serializing
Unity có khả năng serialize các biến, chuyển đổi dữ liệu thành một định dạng có thể chỉnh sửa từ trình soạn thảo Unity. Quá trình serialization phụ thuộc vào các thuộc tính hoặc các trình điều khiển truy cập được áp dụng cho biến.

Nếu một biến là public, nó sẽ được tự động serialize:

```csharp
public int age = 10;
```

Nếu bạn không muốn biến public được serialize, bạn có thể sử dụng thuộc tính NonSerialized từ namespace System như sau:

```csharp
[NonSerialized] public int age = 10;
```

Biến private không được serialize mặc định. Tuy nhiên, nếu bạn muốn chúng được serialize, Unity có một thuộc tính gọi là SerializeField trong namespace Unity. Bạn có thể áp dụng nó như sau:

```csharp
[SerializeField] private int age = 10;
```
## Khởi tạo
Các đối tượng game mới có thể được chèn vào cảnh một cách tự động thông qua việc gọi hàm sau. Hàm này có ba đối số.

- Đối tượng Game - The Game Object 
- (Optional) Vị trí Toàn cầu - Global Position
- (Optional) Quay - Rotation
```csharp
Instantiate(someGameObject);
Instantiate(someGameObject, new Vector3(0, 0, 10));
Instantiate(someGameObject, new Vector3(0, 0, 10), Quaternion.identity);
```
## Tìm Đối Tượng Trong Game
Lớp GameObject có một số phương thức để tìm kiếm đối tượng game trong cấu trúc thư mục.

- Find() - Tìm kiếm một đối tượng game dựa trên tên của nó.
- FindGameObjectsWithTag() - Tìm nhiều đối tượng game được lưu trữ trong một mảng và trả về. Sử dụng tag của đối tượng game để tìm chúng.
- FindWithTag() - Tìm một đối tượng game dựa trên tag của nó.
```csharp
GameObject myObj = GameObject.Find("NAME IN HIERARCHY");
GameObject myObj = GameObject.FindGameObjectsWithTag("TAG");
GameObject myObj = GameObject.FindWithTag("TAG");
```

## Hủy Đối Tượng Trò Chơi
Đối tượng game có thể bị hủy bằng cách gọi hàm Destroy():
```csharp
Destroy(gameObject);
```
## Các Thành Phần (Components)
Các đối tượng game tự nhiên không có nhiều chức năng. Chúng ta cần thêm các thành phần để có các chức năng cụ thể. Nếu bạn đang sử dụng các thành phần tùy chỉnh và cần chọn lựa các thành phần khác, Unity cung cấp cách để lấy chúng. Phương pháp đầu tiên là sử dụng hàm GetComponent(), thường bằng cách chỉ định tên lớp thành phần.
```csharp
AudioSource audioSource = GetComponent<AudioSource>();
```
Hoặc bạn có thể sử dụng từ khóa typeof và xác nhận giá trị như sau:
```csharp
AudioSource audioSource = GetComponent(typeof(AudioSource)) as AudioSource;
```
Cuối cùng, bạn có thể truyền vào tên của thành phần dưới dạng chuỗi như sau:
```csharp
AudioSource audioSource = GetComponent("AudioSource") as AudioSource;
```
## Hằng Số (Constants)
Trong Unity, bạn có thể sử dụng hằng số để định nghĩa các giá trị giữ nguyên trong toàn bộ kịch bản của bạn. Dưới đây là cách bạn có thể sử dụng hằng số trong Unity:

1. Khai Báo Một Hằng Số:
Sử dụng từ khoá const để khai báo một hằng số. Hằng số phải được khởi tạo giá trị tại thời điểm khai báo và không thể thay đổi sau đó. Dưới đây là một ví dụ:
```csharp
public class ExampleScript : MonoBehaviour
{
    // Define a constant for gravity
    private const float Gravity = 9.8f;

    void Start()
    {
        // Use the constant in your code
        float fallSpeed = Gravity * Time.deltaTime;
    }
}
```
2. Lợi Ích của Hằng Số:
Hằng số mang lại những lợi ích quan trọng khi định nghĩa các giá trị được sử dụng ở nhiều nơi trong mã của bạn và không nên được sửa đổi trong thời gian chạy. Chúng giúp mã của bạn trở nên dễ đọc và dễ bảo trì hơn.

3. Sử Dụng Trong Unity:
Bạn có thể sử dụng hằng số trong nhiều kịch bản Unity khác nhau, chẳng hạn như các kịch bản MonoBehaviour được đính kèm vào GameObjects hoặc các kịch bản tiện ích. Hằng số thường được sử dụng cho các giá trị như tốc độ mặc định, kích thước cố định hoặc các tham số không thay đổi khác.

4. Phạm Vi của Hằng Số:
Hằng số có phạm vi giới hạn trong lớp hoặc phương thức mà chúng được khai báo. Nếu bạn cần hằng số có thể truy cập từ nhiều kịch bản, hãy xem xét việc sử dụng một lớp public static.

Dưới đây là một ví dụ đơn giản:
```csharp
public static class GameConstants
{
    public const int MaxScore = 100;
}

public class ScoreManager : MonoBehaviour
{
    void Update()
    {
        // Access the constant from another script
        int currentScore = CalculateScore();
        if (currentScore >= GameConstants.MaxScore)
        {
            Debug.Log("You reached the maximum score!");
        }
    }

    int CalculateScore()
    {
        // Your score calculation logic here
        return 50;
    }
}
```
## Vectors
Vectors quyết định vị trí của các đối tượng trong game và hỗ trợ trong các phép tính về khoảng cách và chuyển động. Unity có hai lớp vector: Vector2 cho các trò chơi 2D với tọa độ (x, y), và Vector3 cho các trò chơi 3D với tọa độ (x, y, z). Trong các lớp này, X đại diện cho Bên trái/Phải, Y biểu thị Lên/Xuống, và Z cho Tiến lên/Lùi lại. Unity cung cấp các hằng số có thể truy cập từ lớp vector tương ứng.
#### Vector 3
```csharp
Vector3 V = new Vector3(0f; 0f; 0f);
```
```csharp
Vector3.right /* (1, 0, 0)  */
Vector3.left /* (-1, 0, 0)  */
Vector3.up /* (0, 1, 0)  */
Vector3.down /* (0, -1, 0)  */
Vector3.forward /* (0, 0, 1)  */
Vector3.back /* (0, 0, -1) */
Vector3.zero /* (0, 0, 0)  */
Vector3.one /* (1, 1, 1)  */
```
#### Vector 2

```csharp
Vector2.right /* (1, 0)  */
Vector2.left  /* (-1, 0) */
Vector2.up    /* (0, 1)  */
Vector2.down  /* (0, -1) */
Vector2.zero  /* (0, 0)  */
Vector2.one   /* (1, 1)  */
```
Nếu bạn chỉ quan tâm đến hướng của một vector cụ thể, bạn có thể truy cập thuộc tính normalized của nó như sau:
```csharp
myVector.normalized
```
Khoảng cách giữa hai vector có thể được tính bằng phương thức Vector3.Distance(), trả về một giá trị kiểu float:
```csharp
float distance = Vector3.Distance(vectorOne, vectorTwo);
```
### Quaternion
Quaternions điều khiển xoay của game object. Bạn có thể kiểm tra hoặc thay đổi xoay của đối tượng bằng cách sử dụng transform.rotation. Hàm Quaternion.LookRotation() của Unity tạo ra một xoay dựa trên một vị trí mục tiêu.
```csharp
Quaternion.LookRotation(gameObjectPosition);
```
Một xoay 30 độ quanh trục y:
```csharp
Quaternion rotation = Quaternion.Euler(0, 30, 0);
```
### Góc Euler
Góc Euler là "góc độ" như 90, 180, 45, 30 độ. Tuy nhiên, quaternion khác biệt so với góc Euler ở chỗ nó biểu diễn một điểm trên Mặt cầu Đơn vị (bán kính là 1 đơn vị).

Ví dụ sử dụng Quaternion để biểu diễn 30 độ xoay quanh trục X và 10 độ xoay quanh trục Y:
```csharp
Quaternion rotation = Quaternion.Euler(30, 10, 0);
```
Sử dụng một Vector để biểu diễn cũng là một cách khác:
```csharp
Vector3 EulerRotation = new Vector3(30, 10, 0);
Quaternion rotation = Quaternion.Euler(EulerRotation);
```
Chuyển đổi góc Quaternion của một transform thành góc Euler
```csharp
Quaternion quaternionAngles = transform.rotation;
Vector3 eulerAngles = quaternionAngles.eulerAngles;
```
Ưu và nhược điểm của góc Euler
Ưu điểm:

- Dễ hiểu và trực quan: Dễ dàng để con người hiểu và làm việc với, đặc biệt là khi xử lý các phép quay đơn giản.
- Dễ sử dụng: Unity cung cấp các phương thức và thuộc tính trực tiếp để làm việc với góc Euler.
Nhược điểm:

- Gimbal Lock: Đây là hiện tượng khi hai trong ba trục của phép quay bị thẳng hàng, dẫn đến mất một bậc tự do trong chuyển động. Điều này gây khó khăn khi thực hiện các phép quay phức tạp.
Giải pháp thay thế
- Khi gặp vấn đề về Gimbal Lock, một giải pháp thay thế là sử dụng quaternions. Unity hỗ trợ mạnh mẽ việc làm việc với quaternions thông qua thuộc tính transform.rotation.
  Ví dụ :
```csharp
  // Đặt góc quay bằng quaternion
transform.rotation = Quaternion.Euler(30, 45, 60);

// Lấy quaternion hiện tại và chuyển đổi sang góc Euler
Quaternion currentRotation = transform.rotation;
Vector3 currentEulerAngles = currentRotation.eulerAngles;
```
### Giữ Tỉ Lệ Màn Hình
Việc giữ tỉ lệ màn hình trong Unity giúp đảm bảo rằng hình ảnh nền (background) hoặc các đối tượng khác sẽ được hiển thị một cách nhất quán và đúng tỷ lệ trên nhiều loại màn hình và độ phân giải khác nhau. Dưới đây là một số lý do chính để giữ tỉ lệ màn hình:

1. Đảm bảo Trải Nghiệm Người Dùng Thống Nhất:

 Khi trò chơi của bạn được chơi trên các thiết bị khác nhau (điện thoại, máy tính bảng, màn hình máy tính), giữ tỉ lệ màn hình giúp đảm bảo rằng nội dung sẽ được hiển thị đúng cách, không bị méo mó hoặc cắt xén.
Điều này giúp người chơi có trải nghiệm nhất quán bất kể họ sử dụng thiết bị nào.
 Tránh Méo Hình Ảnh:

- Nếu tỷ lệ của nền hoặc đối tượng không khớp với tỷ lệ của màn hình, hình ảnh có thể bị kéo dãn hoặc nén lại, dẫn đến méo mó.
- Giữ tỉ lệ đúng giúp đảm bảo rằng tất cả các hình ảnh sẽ duy trì tỷ lệ ban đầu của chúng, giữ cho đồ họa trông chuyên nghiệp và đẹp mắt.
 Duy Trì Bố Cục Đúng:

- Đối với các trò chơi hoặc ứng dụng có bố cục cụ thể, giữ tỉ lệ màn hình giúp duy trì bố cục dự định của nhà phát triển.
- Điều này rất quan trọng đối với các trò chơi có nhiều yếu tố giao diện người dùng hoặc cảnh quan phức tạp.
 Cải Thiện Hiệu Suất:

- Việc tính toán và giữ tỉ lệ màn hình có thể giúp tối ưu hóa hiệu suất bằng cách tránh việc cần phải tái tạo lại các hình ảnh hoặc đối tượng không cần thiết khi kích thước màn hình thay đổi.
- Điều này giúp giảm tải cho CPU và GPU, cải thiện hiệu suất tổng thể của ứng dụng.
Thích Ứng Với Các Thiết Bị Khác Nhau:

- Với sự đa dạng của các thiết bị hiện nay, từ điện thoại thông minh đến máy tính bảng và màn hình độ phân giải cao, giữ tỉ lệ màn hình giúp ứng dụng của bạn có thể thích ứng tốt hơn với sự khác biệt này.
- Đảm bảo rằng trò chơi hoặc ứng dụng của bạn có thể chạy mượt mà trên nhiều thiết bị khác nhau mà không gặp vấn đề về hiển thị.
```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ScaleBackground : MonoBehaviour
{
    private SpriteRenderer background; // Biến để lưu trữ thành phần SpriteRenderer của nền
    private Camera cam; // Biến để lưu trữ thành phần Camera chính

    void Start()
    {
        background = GetComponent<SpriteRenderer>(); // Lấy thành phần SpriteRenderer của đối tượng hiện tại
        cam = Camera.main; // Lấy thành phần Camera chính

        // Lấy kích thước của camera
        float cameraHeight = 2f * cam.orthographicSize; // Chiều cao của camera, orthographicSize là nửa chiều cao của camera
        float cameraWidth = cameraHeight * cam.aspect; // Chiều rộng của camera, được tính bằng chiều cao nhân với tỷ lệ khung hình của camera

        // Lấy kích thước của nền hiện tại
        float bgHeight = background.sprite.bounds.size.y; // Chiều cao của nền (sprite)
        float bgWidth = background.sprite.bounds.size.x; // Chiều rộng của nền (sprite)

        // Tính tỉ lệ tỷ lệ
        float scaleX = cameraWidth / bgWidth; // Tỷ lệ thay đổi theo chiều rộng
        float scaleY = cameraHeight / bgHeight; // Tỷ lệ thay đổi theo chiều cao

        // Áp dụng tỷ lệ cho nền
        transform.localScale = new Vector3(scaleX, scaleY, 1f); // Đặt tỷ lệ mới cho đối tượng nền
    }
}

```

### Sự Kiện Tùy Chỉnh Trong Unity ( Custom Unity Events )
Các sự kiện tùy chỉnh có thể được tạo ra để giúp bạn giao tiếp giữa các đối tượng game khác nhau. Đầu tiên, bạn cần nhập không gian tên chính xác:
```csharp
using UnityEngine.Events;
```
Tiếp theo, bạn có thể tạo một sự kiện tùy chỉnh bằng cách định nghĩa một biến với kiểu "UnityEvent" như sau:
```csharp
public event UnityEvent OnCustomEvent;
```
Unity còn có một kiểu dữ liệu khác gọi là UnityAction để tạo ra các sự kiện tùy chỉnh:
```csharp
public event UnityAction OnCustomEvent;
```
Sự khác biệt chính là kiểu UnityEvent có thể được tuần tự hóa vào trong Unity editor. Nếu bạn không cần sự kiện có thể sửa đổi công khai thông qua Unity editor, bạn nên sử dụng kiểu UnityAction.

Bạn có thể sử dụng generics để gửi thêm dữ liệu với sự kiện của bạn. Tối đa 4 kiểu dữ liệu được hỗ trợ.
```csharp
// 1 Tham số
public event UnityAction<int> OnCustomEvent;

// 2 Tham số
public event UnityAction<int, float> OnCustomEvent;

// 3 Tham số
public event UnityAction<int, float, bool> OnCustomEvent;

// 4 Tham số
public event UnityAction<int, float, bool, string> OnCustomEvent;
```
###Đối Tượng Scriptable (Scriptable Objects)
Đối tượng Scriptable là các container dữ liệu. Chúng có thể là một cách tuyệt vời để tập trung hóa dữ liệu có thể được sử dụng trên các đối tượng và thành phần game khác nhau. Bạn có thể tạo một đối tượng Scriptable bằng cách sử dụng lớp 'ScriptableObject' từ không gian tên 'UnityEngine'.
```csharp
using UnityEngine;

[CreateAssetMenu (fileName = "Data", menuName = "Parent Menu/Child Menu", order = 1)]
public class AudioSO : ScriptableObject
{
    // Nội dung của lớp
}
```
Đối tượng Scriptable cho phép người dùng tạo các file từ các lớp này. Bạn có thể thêm một mục menu bằng cách sử dụng thuộc tính CreateAssetMenu, có các tham số sau:
```csharp
fileName - Tên của file được tạo bởi Unity khi tùy chọn được chọn.
menuName - Tên của menu sẽ được hiển thị trong menu tạo.
order - Thứ tự ưu tiên của mục menu khi được sắp xếp cùng các mục menu khác.
Giải Thích Bổ Sung
Đối tượng Scriptable thường được sử dụng để lưu trữ các dữ liệu độc lập với các instance của đối tượng trong game, chẳng hạn như các thông số cấu hình, dữ liệu tài nguyên, hoặc các bảng dữ liệu. Điều này giúp giảm thiểu sự trùng lặp dữ liệu và tăng cường khả năng tái sử dụng của mã nguồn.

Khi sử dụng đối tượng Scriptable, bạn có thể chỉnh sửa dữ liệu trực tiếp trong Unity editor và các thay đổi sẽ được áp dụng toàn bộ dự án mà không cần khởi tạo lại đối tượng game.
```

## Di Chuyển & Xoay
### Di Chuyển Đối Tượng
#### Transform.Translate()
```csharp
// Cũng có thể nhảy bằng cách đặt nút Space trong Input Manager
public void Translate(Vector3 translation);
public void Translate(Vector3 translation, Space relativeTo = Space.Self);

transform.Translate(Vector3.right * movementSpeed);
```

#### Vector3.MoveTowards()
```csharp
// Tính toán vị trí giữa các điểm được chỉ định bởi current và target
// Di chuyển không xa hơn khoảng cách được chỉ định bởi maxDistanceDelta
public static Vector3 MoveTowards(Vector3 current, Vector3 target, float maxDistanceDelta);

Vector3 targetPosition;
transform.position = Vector3.MoveTowards(transform.position, targetPosition, Time.deltaTime);
```

#### Vector3.Lerp()
```csharp
// Nội suy tuyến tính giữa hai điểm. Kết quả là một chuyển động mượt mà.
public static Vector3 Lerp(Vector3 startValue, Vector3 endValue, float interpolationRatio);

Vector3 targetPosition;
float t = 0;
t += Time.deltaTime * speed;
transform.position = Vector3.Lerp(transform.position, targetPosition, t);
```

#### Vector3.SmoothDamp()
```csharp
// Dần dần thay đổi một vector đến một mục tiêu mong muốn trong thời gian.
// Vector được làm mịn bằng một hàm giống như lò xo-dẫn, sẽ không bao giờ vượt quá.
// Sử dụng phổ biến nhất là để làm mịn cho camera theo dõi.
public static Vector3 SmoothDamp(Vector3 current, Vector3 target, ref Vector3 currentVelocity, float smoothTime, float maxSpeed = Mathf.Infinity, float deltaTime = Time.deltaTime);

float smoothTime = 1f;
Vector3 velocity;
Vector3 targetPosition = target.TransformPoint(new Vector3(0, 5, -10));
// Di chuyển mượt mà camera đến vị trí mục tiêu đó
transform.position = Vector3.SmoothDamp(transform.position, targetPosition, ref velocity, smoothTime);
```

### Xoay Đối Tượng
#### Transform.rotation
```csharp
// Một Quaternion lưu trữ sự quay của Transform trong không gian thế giới.
// Quaternions dựa trên số phức và không gặp vấn đề gimbal lock.
// Unity sử dụng Quaternion để biểu diễn tất cả các phép quay nội tại.

transform.rotation = new Quaternion(rotx, roty, rotz, rotw);
```

#### Transform.eulerAngles
```csharp
// Transform.eulerAngles biểu diễn phép quay trong không gian thế giới. 
// Quan trọng để hiểu rằng mặc dù bạn cung cấp các giá trị quay X, Y và Z để mô tả phép quay của bạn
// những giá trị đó không được lưu trữ trong phép quay. Thay vào đó, các giá trị X, Y & Z được chuyển đổi vào định dạng nội tại của Quaternion.

transform.eulerAngles = Vector3(rotx, roty, rotz);
```

#### Transform.Rotate()
```csharp
// Áp dụng phép quay xung quanh tất cả các trục được cung cấp.
public void Rotate(Vector3 eulers, Space relativeTo = Space.Self);
public void Rotate(float xAngle, float yAngle, float zAngle, Space relativeTo = Space.Self);

transform.Rotate(rotx, roty, rotz);
```

#### Transform.RotateAround()
```csharp
// Quay đối tượng xung quanh trục đi qua điểm trong tọa độ thế giới với góc quay là angle độ.
public void RotateAround(Vector3 point, Vector3 axis, float angle);

// Xoay đối tượng xung quanh mục tiêu ở 20 độ/giây.
Transform target;
transform.RotateAround(target.position, Vector3.up, 20 * Time.deltaTime);
```

#### Transform.LookAt()
```csharp
// Chỉ hướng phía trước ('Z' tích cực) của đối tượng đến một vị trí trong không gian thế giới.
public void LookAt(Transform target);
public void LookAt(Transform target, Vector3 worldUp = Vector3.up);

// Quay vector phía trước của đối tượng để chỉ đến Transform mục tiêu.
Transform target;
transform.LookAt(target);

// Giống như trên, nhưng đặt tham số worldUp thành Vector3.left trong ví dụ này làm cho đối tượng nghiêng về một bên.
transform.LookAt(target, Vector3.left);
```

#### Quaternion.LookRotation()
```csharp
// Tạo một quay xoay với hướng cụ thể của forward và upwards được chỉ định.
public static Quaternion LookRotation(Vector3 forward, Vector3 upwards = Vector3.up);

// Đoạn mã dưới đây quay đối tượng hướng về một đối tượng mục tiêu.
Vector3 direction = target.position - transform.position;
Quaternion rotation = Quaternion.LookRotation(direction);
transform.rotation = rotation;
```

#### Quaternion.FromToRotation()
```csharp
// Tạo ra một quay (Quaternion) xoay từ hướng fromDirection đến toDirection.
public static Quaternion FromToRotation(Vector3 fromDirection, Vector3 toDirection);

// Đặt quay sao cho trục y của transform nằm dọc theo trục z.
transform.rotation = Quaternion.FromToRotation(Vector3.up, transform.forward);
```

#### Quaternion.ToAngleAxis()
```csharp
// Chuyển đổi quay thành biểu diễn góc-trục (góc theo đơn vị độ).
// Nói cách khác, trích xuất góc cũng như trục mà quaternion này đại diện.
public void ToAngleAxis(out float angle, out Vector3 axis);

// Trích xuất góc quay - trục từ quay của transform
float angle = 0.0f;
Vector3 axis = Vector3.zero;
transform.rotation.ToAngleAxis(out angle, out axis);
```
## Time
Unity hỗ trợ các hoạt động liên quan đến thời gian thông qua thư viện Time của mình. Các API phổ biến nhất để làm việc với thời gian trong dự án của bạn là Time.time, Time.deltaTime và Time.timeScale.

- Time.time trả về thời gian tại đầu khung hình hiện tại.
- Time.deltaTime trả về sự khác biệt thời gian giữa khung hình hiện tại và khung hình cuối cùng tính bằng giây.
- Time.timeScale đại diện cho tỷ lệ mà thời gian trôi qua.
```csharp
// Thời gian tính bằng giây kể từ khi bắt đầu trò chơi
float timeSinceStartOfGame = Time.time;
// Tỷ lệ mà thời gian đang trôi qua
float currentTimeScale = Time.timeScale;
// Tạm dừng thời gian
Time.timeScale = 0;
// Thời gian tính bằng giây để hoàn thành khung hình cuối cùng
// Sử dụng trong Update() và LateUpdate()
float timePassedSinceLastFrame = Time.deltaTime;
// Khoảng thời gian tính bằng giây mà các cập nhật vật lý và tốc độ khung hình cố định được thực hiện mỗi giây
float physicsInterval = Time.fixedDeltaTime;

```
Mẹo:

- Sử dụng Time.time để theo dõi thời gian tổng cộng đã trôi qua trong trò chơi của bạn.
- Time.deltaTime rất hữu ích khi bạn cần tính toán tốc độ của các đối tượng di chuyển.
- Time.timeScale cho phép bạn làm chậm lại hoặc tăng tốc thời gian trong trò chơi của bạn.
## Rendering materials
Vật liệu kết xuất : Vật liệu cho biết cách bề mặt sẽ được kết xuất trong cảnh. Vật liệu chứa các tham chiếu đến shaders, textures, màu sắc, phát sáng và nhiều thứ khác. Mỗi vật liệu yêu cầu một shader để kết xuất nội dung và các thuộc tính có sẵn cho vật liệu đó có thể thay đổi tùy thuộc vào các giá trị shader khác nhau.
```csharp
[SerializeField] Material material;
[SerializeField] Texture2D texture;
[SerializeField] Color color = Color.red;

// Start được gọi trước khi cập nhật khung hình đầu tiên
void Start() {
    MeshRenderer meshRenderer = GetComponent<MeshRenderer>();
    // Thay đổi vật liệu, texture, màu sắc và shader tại runtime
    meshRenderer.material = material;
    meshRenderer.material.mainTexture = texture;
    meshRenderer.material.color = color;
    meshRenderer.material.SetColor("_Color", Color.blue);
    meshRenderer.material.EnableKeyword("_EMISSION");
    meshRenderer.material.SetColor("_EmissionColor", Color.yellow);
    meshRenderer.material.shader = Shader.Find("Standard (Specular setup)");
}
```
Mẹo:

- Bạn có thể thay đổi các thuộc tính của vật liệu như texture và màu sắc tại runtime để tạo ra các hiệu ứng đặc biệt.
- Sử dụng Shader.Find() để tìm và áp dụng shader phù hợp cho vật liệu của bạn.
## Lighting
Lighting là một thành phần bắt buộc trong bất kỳ cảnh Unity nào. Tất cả các cảnh của Unity chứa một thành phần ánh sáng định hướng theo mặc định. Unity có bốn loại ánh sáng - định hướng, điểm, đèn pha và ánh sáng khu vực.
```csharp
[SerializeField] LightType lightType = LightType.Directional;
Light lightComp = null;

// Start được gọi trước khi cập nhật khung hình đầu tiên
void Start() {
    GameObject lightGameObject = new GameObject("The Light");
    lightComp = lightGameObject.AddComponent<Light>();
    lightComp.color = Color.blue;
    lightComp.type = lightType;
    lightGameObject.transform.position = new Vector3(0, 5, 0);
}

void Update() {
    if (Input.GetKey(KeyCode.UpArrow)) {
        lightComp.GetComponent<Light>().enabled = true;
    }
    if (Input.GetKey(KeyCode.DownArrow)) {
        lightComp.GetComponent<Light>().enabled = false;
    }
}
```
Mẹo:

- Sử dụng LightType.Directional để mô phỏng ánh sáng mặt trời.
- Bạn có thể điều chỉnh vị trí và màu sắc của ánh sáng để đạt được hiệu ứng chiếu sáng mong muốn trong cảnh của bạn.
## Coroutine
Coroutine giống như một hoạt động nền có thể giữ việc thực thi mã sau câu lệnh yield cho đến khi nó trả về một giá trị.
```csharp
// Tạo một Coroutine
private IEnumerator CountSeconds(int count = 10) {
    for (int i = 0; i <= count; i++) {
        Debug.Log(i + " giây đã trôi qua");
        yield return new WaitForSeconds(1.0f);
    }
}

// Gọi một Coroutine
StartCoroutine(CountSeconds());
StartCoroutine(CountSeconds(10));

// Lưu trữ và gọi một Coroutine từ một biến
private IEnumerator countSecondsCoroutine;
countSecondsCoroutine = CountSeconds();
StartCoroutine(countSecondsCoroutine);

// Dừng một Coroutine đã lưu trữ
StopCoroutine(countSecondsCoroutine);

// Các loại Coroutine trả về
// Chờ đến khi frame tiếp theo gọi Update()
yield return null;
// Chờ đến khi gọi FixedUpdate() tiếp theo
yield return new WaitForFixedUpdate();
// Chờ đến khi tất cả các khung hình trong frame này đã được thực thi
yield return new WaitForEndOfFrame();
// Chờ thời gian trong trò chơi tính bằng giây
yield return new WaitForSeconds(1.0f);
// Chờ đến khi một điều kiện tùy chỉnh được đáp ứng
yield return new WaitUntil(() => MY_CONDITION);
// Chờ cho một yêu cầu web
yield return new WWW("MY/WEB/REQUEST");
// Chờ đến khi một Coroutine khác hoàn thành
yield return StartCoroutine("MY_COROUTINE");

```
Mẹo:

- Coroutine rất hữu ích để xử lý các công việc cần đợi một khoảng thời gian nhất định hoặc cần đợi một điều kiện nào đó hoàn thành.
- Bạn có thể sử dụng các loại yield khác nhau để kiểm soát thời gian chờ và điều kiện chờ.
## Physics
### Raycast
Raycast là một kỹ thuật trong lập trình game và đồ họa máy tính được sử dụng để xác định xem có bất kỳ đối tượng nào trong không gian ba chiều giao với một tia (ray) được bắn từ một điểm nhất định theo một hướng nhất định. Trong Unity, raycast thường được sử dụng để phát hiện va chạm, kiểm tra đường thẳng tầm nhìn, và nhiều tác vụ khác liên quan đến phát hiện không gian.

Sử dụng Raycast trong Unity
- Khái niệm cơ bản: Một tia (ray) được bắn từ một điểm xuất phát theo một hướng nhất định. Nếu tia này giao với bất kỳ collider nào trong không gian ba chiều, thông tin về va chạm sẽ được trả về.
Các tham số chính:
- Origin (gốc tọa độ): Điểm xuất phát của tia.
- Direction (hướng): Hướng của tia.
- MaxDistance (khoảng cách tối đa): Khoảng cách tối đa mà tia sẽ bắn.
- LayerMask (mặt nạ lớp): Chỉ định các lớp (layer) mà tia sẽ kiểm tra va chạm.
```csharp
void FixedUpdate() {
    // Dịch chuyển bit của chỉ số lớp (8) để tạo ra một mặt nạ bit
    int layerMask = 1 << 8;

    // Điều này sẽ chỉ bắn tia vào các collider trong lớp 8.
    // Nhưng thay vào đó chúng ta muốn va chạm với mọi thứ trừ lớp 8. Toán tử ~ thực hiện điều này, nó đảo ngược một mặt nạ bit.
    layerMask = ~layerMask;

    RaycastHit hit;
    // Kiểm tra xem tia có giao với bất kỳ đối tượng nào ngoại trừ lớp người chơi hay không
    if (Physics.Raycast(transform.position, transform.TransformDirection(Vector3.forward), out hit, Mathf.Infinity, layerMask)) {
        Debug.DrawRay(transform.position, transform.TransformDirection(Vector3.forward) * hit.distance, Color.yellow);
        Debug.Log("Đã chạm");
    }
}
```
Giải thích:

- void FixedUpdate(): Phương thức FixedUpdate được Unity gọi theo các khoảng thời gian cố định, phù hợp cho các tính toán vật lý. Điều này đảm bảo rằng các tính toán vật lý không bị ảnh hưởng bởi tốc độ khung hình.
- int layerMask = 1 << 8;: Dịch chuyển bit của số 1 sang trái 8 lần để tạo ra mặt nạ bit cho lớp 8. Mặt nạ bit này chỉ định rằng tia ray sẽ chỉ kiểm tra va chạm với các đối tượng trong lớp 8.
- layerMask = ~layerMask;: Đảo ngược mặt nạ bit để tia ray sẽ kiểm tra va chạm với tất cả các lớp ngoại trừ lớp 8. Toán tử ~ đảo ngược tất cả các bit trong mặt nạ bit.
- RaycastHit hit;: Khai báo một biến RaycastHit để lưu trữ thông tin về đối tượng bị tia ray trúng.
- if (Physics.Raycast(transform.position, transform.TransformDirection(Vector3.forward), out hit, Mathf.Infinity, layerMask)): Bắn một tia từ vị trí hiện tại của đối tượng theo hướng phía trước (forward). Nếu tia này trúng một đối tượng nào đó (ngoại trừ lớp 8), thông tin về đối tượng đó sẽ được lưu vào biến hit.
- transform.position: Vị trí hiện tại của đối tượng.
- transform.TransformDirection(Vector3.forward): Chuyển đổi hướng phía trước từ không gian cục bộ sang không gian thế giới.
- out hit: Tham số đầu ra để lưu trữ thông tin về đối tượng bị tia ray trúng.
- Mathf.Infinity: Chiều dài của tia ray là vô hạn.
- layerMask: Mặt nạ lớp để chỉ định các lớp nào sẽ bị kiểm tra va chạm.
- Debug.DrawRay(transform.position, transform.TransformDirection(Vector3.forward) * hit.distance, Color.yellow);: Vẽ một tia màu vàng từ vị trí hiện tại của đối tượng theo hướng phía trước với chiều dài là khoảng cách đến đối tượng bị tia ray trúng. Điều này giúp trực quan hóa tia ray trong không gian 3D.
- Debug.Log("Đã chạm");: In ra thông báo "Đã chạm" trong bảng điều khiển (console) nếu tia ray trúng một đối tượng.

  
   Tóm lại: Raycast được sử dụng để kiểm tra xem có bất kỳ đối tượng nào giao với một tia bắn từ một điểm xuất phát theo một hướng nhất định.
### IgnoreCollision
IgnoreCollision là một phương thức trong Unity cho phép bạn làm cho hệ thống phát hiện va chạm bỏ qua các va chạm giữa hai collider cụ thể. Điều này rất hữu ích khi bạn muốn hai đối tượng không tương tác với nhau thông qua hệ thống vật lý, ví dụ như đạn và người chơi trong cùng một đội.

Sử dụng IgnoreCollision trong Unity
- Cú pháp: Physics.IgnoreCollision(Collider collider1, Collider collider2, bool ignore = true)
- Collider collider1: Collider của đối tượng đầu tiên.
- Collider collider2: Collider của đối tượng thứ hai.
- bool ignore: Tham số tùy chọn xác định liệu các va chạm nên bị bỏ qua (true) hay không (false).
```csharp
// Làm cho hệ thống phát hiện va chạm bỏ qua tất cả các va chạm giữa collider1 và collider2.
public static void IgnoreCollision(Collider collider1, Collider collider2, bool ignore = true);

// Ở đây chúng ta đang vô hiệu hóa phát hiện va chạm giữa các collider của các đối tượng ally và bullet.
Transform bullet;
Transform ally;
Physics.IgnoreCollision(bullet.GetComponent<Collider>(), ally.GetComponent<Collider>());

```
Giải thích:

- public static void IgnoreCollision(Collider collider1, Collider collider2, bool ignore = true);: Phương thức tĩnh IgnoreCollision của lớp Physics làm cho hệ thống phát hiện va chạm bỏ qua tất cả các va chạm giữa collider1 và collider2.
- Collider collider1: Collider đầu tiên.
- Collider collider2: Collider thứ hai.
- bool ignore = true: Tham số tùy chọn xác định liệu các va chạm nên bị bỏ qua (true) hay không (false).
- Transform bullet;: Khai báo biến bullet để lưu trữ thành phần Transform của đối tượng đạn.
- Transform ally;: Khai báo biến ally để lưu trữ thành phần Transform của đối tượng đồng minh.
- Physics.IgnoreCollision(bullet.GetComponent<Collider>(), ally.GetComponent<Collider>());: Gọi phương thức IgnoreCollision để vô hiệu hóa phát hiện va chạm giữa collider của đối tượng đạn và đồng minh.
- bullet.GetComponent<Collider>(): Lấy thành phần Collider của đối tượng đạn.
- ally.GetComponent<Collider>(): Lấy thành phần Collider của đối tượng đồng minh.

  
  Tóm lại: IgnoreCollision được sử dụng để vô hiệu hóa phát hiện va chạm giữa hai collider cụ thể, giúp bạn kiểm soát tốt hơn các tương tác vật lý giữa các đối tượng trong trò chơi.
## Input

### Bàn Phím

```csharp
// Trả về true trong suốt frame khi người dùng bắt đầu nhấn xuống phím
if (Input.GetKeyDown(KeyCode.Space)) {
    Debug.Log("Space key was pressed");
}

// Chức năng nhảy cũng được đặt cho phím Space trong Input Manager
if (Input.GetButtonDown("Jump")) {
    Debug.Log("Do something");
}
```

### Chuột

```csharp
if (Input.GetAxis("Mouse X") < 0) {
    Debug.Log("Mouse moved left");
}

if (Input.GetAxis("Mouse Y") > 0) {
    Debug.Log("Mouse moved up");
}

if (Input.GetMouseButtonDown(0)) {
    Debug.Log("Pressed primary button.");
}

if (Input.GetMouseButtonDown(1)) {
    Debug.Log("Pressed secondary button.");
}

if (Input.GetMouseButtonDown(2)) {
    Debug.Log("Pressed middle click.");
}
```

### Chạm
```csharp
if (Input.touchCount > 0) {
    touch = Input.GetTouch(0);

    if (touch.phase == TouchPhase.Began) {
        Debug.Log("Touch began");
    }

    if (touch.phase == TouchPhase.Moved) {
        Debug.Log("Touch moves");
    }

    if (touch.phase == TouchPhase.Ended) {
        Debug.Log("Touch ended");
    }
}
```

## Giao Diện Người Dùng (UI)

```csharp

### Nút (Button)
// Button được sử dụng để xử lý sự nhấn và tương tác của người dùng.
// Gắn kịch bản này vào một thành phần Button để phản ứng với sự nhấp vào nút.

using UnityEngine.UI;

Button myButton = GetComponent<Button>();
myButton.onClick.AddListener(MyButtonClickHandler);

void MyButtonClickHandler() {
    Debug.Log("Button Clicked!");
}
```

### Thanh Trượt (Slider)
```csharp
// Slider được sử dụng để chọn một giá trị trong khoảng.
// Gắn kịch bản này vào một thành phần Slider để phản ứng với sự thay đổi giá trị.

using UnityEngine.UI;

Slider mySlider = GetComponent<Slider>();
mySlider.onValueChanged.AddListener(MySliderValueChangedHandler);

void MySliderValueChangedHandler(float value) {
    Debug.Log("Slider Value: " + value);
}
```

## Âm Thanh

### Chơi Âm Thanh Cơ Bản

```csharp
public class PlayAudio : MonoBehaviour {
    public AudioSource audioSource;

    void Start() {
        // Gọi Play trên một Audio Source đang phát sẽ khiến nó bắt đầu từ đầu.
        audioSource.Play();
    }
}
```


## Mô Hình Thiết Kế
- Tóm lại: Các mẫu thiết kế này giúp giải quyết các vấn đề phổ biến trong lập trình và thiết kế phần mềm, giúp mã của bạn dễ bảo trì, mở rộng và dễ hiểu hơn.
### Singleton
Mẫu thiết kế Singleton : Mẫu thiết kế Singleton đảm bảo rằng một lớp chỉ có một thể hiện duy nhất và cung cấp một điểm truy cập toàn cục tới nó. Điều này rất hữu ích khi bạn cần một đối tượng toàn cục duy nhất trong suốt ứng dụng của bạn, chẳng hạn như một kết nối cơ sở dữ liệu hoặc một đối tượng cấu hình.
```csharp
// Định nghĩa lớp singleton
public class SingletonClass : MonoBehaviour {
    private static SingletonClass instance;

    public static SingletonClass Instance { get { return instance; } }

    private void Awake() {
        if (instance != null && instance != this) {
            Destroy(this.gameObject);
        } else {
            instance = this;
        }
    }

    private void SomeFunction() {
    }
}

// Sử dụng nó trong một lớp khác
public class AnotherClass : MonoBehaviour {

    private void Awake() {
       SingletonClass.Instance.SomeFunction();
    }
}
```
Giải thích:

- 'SingletonClass'  đảm bảo chỉ có một thể hiện của lớp này tồn tại bằng cách kiểm tra và gán biến 'instance' trong phương thức 'Awake'.
- Nếu một thể hiện khác tồn tại, nó sẽ bị hủy.
- 'AnotherClass' gọi phương thức 'SomeFunction' của 'SingletonClass' thông qua 'SingletonClass.Instance'.
### Factory Pattern
Mẫu thiết kế Factory : Mẫu thiết kế Factory cung cấp một cách để tạo các đối tượng mà không cần chỉ ra lớp chính xác của đối tượng sẽ được tạo. Điều này cho phép bạn tạo ra các đối tượng mà không cần phụ thuộc vào lớp cụ thể của chúng, giúp mã của bạn linh hoạt hơn và dễ dàng mở rộng.
```csharp
// Interface cho kẻ thù
public interface IEnemy {
    void Attack();
    void TakeDamage(int damage);
}

// Triển khai cụ thể của kẻ thù: Goblin
public class Goblin : IEnemy {
    public void Attack() => Debug.Log("Goblin đang tấn công!");
    public void TakeDamage(int damage) => Debug.Log($"Goblin nhận {damage} sát thương.");
}

// Triển khai cụ thể của kẻ thù: Orc
public class Orc : IEnemy {
    public void Attack() => Debug.Log("Orc đang tấn công!");
    public void TakeDamage(int damage) => Debug.Log($"Orc nhận {damage} sát thương.");
}

// Interface nhà máy để tạo kẻ thù
public interface IEnemyFactory {
    IEnemy CreateEnemy();
}

// Triển khai cụ thể của nhà máy: GoblinFactory
public class GoblinFactory : IEnemyFactory {
    public IEnemy CreateEnemy() => new Goblin();
}

// Triển khai cụ thể của nhà máy: OrcFactory
public class OrcFactory : IEnemyFactory {
    public IEnemy CreateEnemy() => new Orc();
}

// Lớp Client sử dụng nhà máy để tạo và tương tác với kẻ thù
public class GameManager : MonoBehaviour {
    private void Start() {
        InteractWithEnemy(new GoblinFactory());
        InteractWithEnemy(new OrcFactory());

        // Bạn có thể giới thiệu các triển khai cụ thể mới của IEnemy
        // mà không cần sửa đổi mã khách hàng hiện có
        // tuân thủ nguyên tắc mở/đóng của thiết kế SOLID 
    }

    private void InteractWithEnemy(IEnemyFactory factory) {
        IEnemy enemy = factory.CreateEnemy();

        // Tương tác nhất quán bất kể loại kẻ thù
        enemy.Attack();
        enemy.TakeDamage(20);
    }
}
```
Giải thích:

- 'IEnemy' định nghĩa giao diện cho các đối tượng kẻ thù.
- 'Goblin' và Orc là các lớp triển khai cụ thể của 'IEnemy'.
- IEnemyFactory định nghĩa giao diện cho nhà máy tạo ra kẻ thù.
- 'GoblinFactory' và 'OrcFactory' là các lớp triển khai cụ thể của 'IEnemyFactory'.
- 'GameManager' sử dụng các nhà máy để tạo và tương tác với các kẻ thù mà không cần biết chi tiết cụ thể của chúng.
  
### Observer Pattern
Mẫu thiết kế Observer :Mẫu thiết kế Observer định nghĩa một sự phụ thuộc một-nhiều giữa các đối tượng để khi một đối tượng thay đổi trạng thái, tất cả các phụ thuộc của nó đều được thông báo và cập nhật tự động. Điều này rất hữu ích cho các hệ thống sự kiện và thông báo thay đổi.
```csharp
// Giao diện Observer
public interface IObserver {
    void UpdateObserver(string message);
}

// Triển khai cụ thể của observer
public class ConcreteObserver : IObserver {
    private string name;

    public ConcreteObserver(string name) {
        this.name = name;
    }

    public void UpdateObserver(string message) {
        Debug.Log($"{name} nhận thông điệp: {message}");
    }
}

// Lớp Subject
public class Subject {
    private List<IObserver> observers = new List<IObserver>();

    public void AddObserver(IObserver observer) {
        observers.Add(observer);
    }

    public void RemoveObserver(IObserver observer) {
        observers.Remove(observer);
    }

    public void NotifyObservers(string message) {
        foreach (var observer in observers) {
            observer.UpdateObserver(message);
        }
    }
}

// Ví dụ về sử dụng
public class ObserverExample : MonoBehaviour {
    private void Start() {
        Subject subject = new Subject();

        ConcreteObserver observer1 = new ConcreteObserver("Observer 1");
        ConcreteObserver observer2 = new ConcreteObserver("Observer 2");

        subject.AddObserver(observer1);
        subject.AddObserver(observer2);

        // Thông báo tất cả các observer
        subject.NotifyObservers("Hello Observers!");
    }
}
```
Giải thích:

- 'IObserver' định nghĩa giao diện cho các 'observer'.
- 'ConcreteObserver' là triển khai cụ thể của 'IObserver'.
- 'Subject' quản lý danh sách các observer và thông báo cho chúng khi có sự thay đổi.
- 'ObserverExample' là ví dụ sử dụng mẫu thiết kế 'Observer', thêm các 'observer' vào 'Subject' và thông báo cho chúng.

### Command Pattern
Mẫu thiết kế Command : Mẫu thiết kế Command chuyển một yêu cầu thành một đối tượng độc lập, chứa tất cả các thông tin về yêu cầu đó. Điều này cho phép bạn tham số hóa các phương thức, trì hoãn hoặc xếp hàng các yêu cầu thực thi, và hỗ trợ hủy bỏ các thao tác.
```csharp
// Giao diện Command
public interface ICommand {
    void Execute();
}

// Các lớp lệnh cụ thể
public class MoveCommand : ICommand {
    private Transform transform;
    private Vector3 direction;
    private float distance;

    public MoveCommand(Transform transform, Vector3 direction, float distance) {
        this.transform = transform;
        this.direction = direction;
        this.distance = distance;
    }

    public void Execute() {
        transform.Translate(direction * distance);
    }
}

// Lớp Invoker
public class CommandInvoker {
    private Stack<ICommand> commandStack = new Stack<ICommand>();

    public void ExecuteCommand(ICommand command) {
        commandStack.Push(command);
        command.Execute();
    }

    public void Undo() {
        if (commandStack.Count > 0) {
            var command = commandStack.Pop();
            // Thực hiện phương thức undo nếu cần thiết
        }
    }
}

// Sử dụng
public class CommandUser : MonoBehaviour {
    private CommandInvoker invoker = new CommandInvoker();

    void Update() {
        if (Input.GetKeyDown(KeyCode.UpArrow)) {
            ICommand moveUp = new MoveCommand(transform, Vector3.up, 1.0f);
            invoker.ExecuteCommand(moveUp);
        }

        // Thêm các hướng khác và invoker.Undo() cho các thao tác undo
    }
}
```
Giải thích:

- ICommand định nghĩa giao diện cho các lệnh.
- MoveCommand là lớp lệnh cụ thể để di chuyển đối tượng.
- CommandInvoker quản lý và thực thi các lệnh.
- CommandUser là lớp sử dụng CommandInvoker để thực thi các lệnh dựa trên đầu vào của người dùng.

### State Pattern
Mẫu thiết kế State : Mẫu thiết kế State cho phép một đối tượng thay đổi hành vi của nó khi trạng thái nội tại của nó thay đổi. Đối tượng sẽ có vẻ như đã thay đổi lớp của nó. Điều này rất hữu ích cho các đối tượng có nhiều trạng thái khác nhau với các hành vi khác nhau.
```csharp
// Giao diện State
public interface IState {
    void Enter();
    void Execute();
    void Exit();
}

// Các lớp trạng thái cụ thể
public class IdleState : IState {
    private readonly StateMachine stateMachine;

    public IdleState(StateMachine stateMachine) {
        this.stateMachine = stateMachine;
    }

    public void Enter() {
        Debug.Log("Vào trạng thái Idle");
    }

    public void Execute() {
        Debug.Log("Thực thi trạng thái Idle");
    }

    public void Exit() {
        Debug.Log("Thoát trạng thái Idle");
    }
}

public class MoveState : IState {
    private readonly StateMachine stateMachine;

    public MoveState(StateMachine stateMachine) {
        this.stateMachine = stateMachine;
    }

    public void Enter() {
        Debug.Log("Vào trạng thái Move");
    }

    public void Execute() {
        Debug.Log("Thực thi trạng thái Move");
    }

    public void Exit() {
        Debug.Log("Thoát trạng thái Move");
    }
}

// Lớp StateMachine
public class StateMachine {
    private IState currentState;

    public void ChangeState(IState newState) {
        if (currentState != null) {
            currentState.Exit();
        }
        currentState = newState;
        currentState.Enter();
    }

    public void Update() {
        if (currentState != null) {
            currentState.Execute();
        }
    }
}

// Lớp Character sử dụng StateMachine
public class Character : MonoBehaviour {
    private StateMachine stateMachine;

    private void Start() {
        stateMachine = new StateMachine();
        stateMachine.ChangeState(new IdleState(stateMachine));
    }

    private void Update() {
        stateMachine.Update();

        // Chuyển trạng thái dựa trên các điều kiện
        if (Input.GetKeyDown(KeyCode.Space)) {
            stateMachine.ChangeState(new MoveState(stateMachine));
        }
    }
}

```
Giải thích:

- IState định nghĩa giao diện cho các trạng thái.
- IdleState và MoveState là các lớp trạng thái cụ thể.
- StateMachine quản lý và chuyển đổi các trạng thái.
- Character sử dụng StateMachine để quản lý các trạng thái của đối tượng dựa trên các điều kiện nhất định.

## Practical Use Cases

### Check if object is on the ground
Kiểm tra nếu đối tượng đang ở trên mặt đất :
```csharp
RaycastHit hit;

// Khác với ví dụ này, hầu hết thời gian bạn nên truyền một layerMask làm tùy chọn cuối cùng để chỉ hit đến mặt đất
if (Physics.Raycast(transform.position, -Vector3.up, out hit, 0.5f)) {
   Debug.Log("Hit something below!"); // Kiểm tra xem có đối tượng nào phía dưới đối tượng hiện tại trong phạm vi 0.5 đơn vị
}
```
Giải thích:

- RaycastHit hit: Đối tượng này lưu trữ thông tin về đối tượng bị chạm bởi tia raycast.
- Physics.Raycast(transform.position, -Vector3.up, out hit, 0.5f): Phương thức này bắn một tia từ vị trí của đối tượng hiện tại xuống dưới (trục Y âm) trong phạm vi 0.5 đơn vị.
- Nếu tia ray gặp phải một đối tượng trong phạm vi này, nó sẽ trả về true và thông báo "Hit something below!" sẽ được ghi ra.
### Get the transform of a Body Bone
Lấy transform của xương cơ thể : 
```csharp
Animator animator;

Transform transform = animator.GetBoneTransform(HumanBodyBones.Head); // Lấy transform của xương đầu từ animator
```
Giải thích:

- Animator animator: Đối tượng Animator được sử dụng để điều khiển các đối tượng 3D.
- animator.GetBoneTransform(HumanBodyBones.Head): Phương thức này lấy transform của xương đầu trong hệ thống xương của nhân vật.
### Make object look at the camera
Làm cho đối tượng nhìn vào camera :
```csharp
var camPosition = Camera.main.transform.position;

transform.rotation = Quaternion.LookRotation(transform.position - camPosition); // Làm cho đối tượng hiện tại xoay để nhìn vào vị trí của camera chính

```
Giải thích:

- var camPosition = Camera.main.transform.position: Lấy vị trí của camera chính.
- transform.rotation = Quaternion.LookRotation(transform.position - camPosition): Đặt góc quay của đối tượng để đối tượng luôn nhìn vào vị trí của camera.

### Load next scene
Tải cảnh tiếp theo : 
```csharp
var nextSceneToLoad = SceneManager.GetActiveScene().buildIndex + 1;
var totalSceneCount = SceneManager.sceneCountInBuildSettings;

if (nextSceneToLoad < totalSceneCount) {
  SceneManager.LoadScene(nextSceneToLoad); // Tải cảnh tiếp theo nếu nó tồn tại
}

```
Giải thích:

- var nextSceneToLoad = SceneManager.GetActiveScene().buildIndex + 1: Lấy chỉ số của cảnh tiếp theo.
- var totalSceneCount = SceneManager.sceneCountInBuildSettings: Lấy tổng số cảnh có trong cài đặt xây dựng.
- if (nextSceneToLoad < totalSceneCount) { SceneManager.LoadScene(nextSceneToLoad); }: Nếu cảnh tiếp theo tồn tại (không vượt quá tổng số cảnh), tải cảnh tiếp theo.

## Save Data
### PlayerPrefs
PlayerPrefs là một hệ thống lưu trữ đơn giản dành cho các giá trị kiểu chuỗi, số nguyên và số thực. Nó thường được sử dụng để lưu trữ cài đặt người dùng hoặc điểm số cao.

Ví dụ:
```csharp
// Lưu điểm số cao
PlayerPrefs.SetInt("HighScore", 100); // Lưu điểm số cao với key là "HighScore"

// Lấy điểm số cao
int highScore = PlayerPrefs.GetInt("HighScore", 0); // Lấy điểm số cao, nếu không có thì trả về 0
Debug.Log("High Score: " + highScore); // In ra điểm số cao

// Lưu sức khỏe người chơi
PlayerPrefs.SetInt("PlayerHealth", 100); // Lưu sức khỏe người chơi với key là "PlayerHealth"

// Lấy sức khỏe người chơi
int playerHealth = PlayerPrefs.GetInt("PlayerHealth", 100); // Lấy sức khỏe người chơi, nếu không có thì trả về 100
Debug.Log("Player Health: " + playerHealth); // In ra sức khỏe người chơi

// Lưu cảnh hiện tại
PlayerPrefs.SetString("CurrentScene", "Level1"); // Lưu tên cảnh hiện tại với key là "CurrentScene"

// Lấy cảnh hiện tại
string currentScene = PlayerPrefs.GetString("CurrentScene", "MainMenu"); // Lấy tên cảnh hiện tại, nếu không có thì trả về "MainMenu"
Debug.Log("Current Scene: " + currentScene); // In ra tên cảnh hiện tại

// Xóa dữ liệu
PlayerPrefs.DeleteKey("HighScore"); // Xóa dữ liệu với key là "HighScore"
PlayerPrefs.DeleteKey("PlayerHealth"); // Xóa dữ liệu với key là "PlayerHealth"
PlayerPrefs.DeleteKey("CurrentScene"); // Xóa dữ liệu với key là "CurrentScene"
```
### ScriptableObject
ScriptableObject là một cách mạnh mẽ để lưu trữ dữ liệu không phụ thuộc vào đối tượng hiện tại trong cảnh. Nó rất hữu ích cho việc tạo các dữ liệu cấu hình hoặc dữ liệu trò chơi có thể được chia sẻ giữa các cảnh.

Ví dụ:
```csharp
using UnityEngine;

// Định nghĩa một ScriptableObject
[CreateAssetMenu(fileName = "GameData", menuName = "ScriptableObjects/GameData", order = 1)]
public class GameData : ScriptableObject
{
    public int playerHealth; // Biến lưu trữ sức khỏe người chơi
    public int playerScore; // Biến lưu trữ điểm số người chơi
    public string currentScene; // Biến lưu trữ tên cảnh hiện tại
}

// Sử dụng ScriptableObject trong một script khác
public class GameManager : MonoBehaviour
{
    public GameData gameData; // Tham chiếu đến đối tượng GameData

    void Start()
    {
        gameData.playerHealth = 100; // Thiết lập sức khỏe người chơi
        gameData.playerScore = 0; // Thiết lập điểm số người chơi
        gameData.currentScene = "Level1"; // Thiết lập tên cảnh hiện tại
    }
}
```
### JSON
Lưu trữ dữ liệu dưới dạng JSON là một cách phổ biến để lưu trữ dữ liệu phức tạp. Bạn có thể dễ dàng chuyển đổi các đối tượng thành chuỗi JSON và ngược lại.

Ví dụ:
```csharp
using System.IO;
using UnityEngine;

// Định nghĩa một lớp dữ liệu
[System.Serializable]
public class PlayerData
{
    public int health; // Biến lưu trữ sức khỏe
    public int score; // Biến lưu trữ điểm số
    public string currentScene; // Biến lưu trữ tên cảnh hiện tại
}

// Lưu dữ liệu vào file JSON
public class SaveLoadManager : MonoBehaviour
{
    public PlayerData playerData; // Tham chiếu đến đối tượng PlayerData

    public void SaveData()
    {
        string json = JsonUtility.ToJson(playerData); // Chuyển đối tượng PlayerData thành chuỗi JSON
        File.WriteAllText(Application.persistentDataPath + "/playerData.json", json); // Lưu chuỗi JSON vào file
    }

    public void LoadData()
    {
        string path = Application.persistentDataPath + "/playerData.json"; // Đường dẫn đến file JSON
        if (File.Exists(path)) // Kiểm tra nếu file tồn tại
        {
            string json = File.ReadAllText(path); // Đọc nội dung file JSON
            playerData = JsonUtility.FromJson<PlayerData>(json); // Chuyển chuỗi JSON thành đối tượng PlayerData
        }
    }
}

```
### Binary
Lưu trữ dữ liệu dưới dạng nhị phân là một cách hiệu quả để lưu trữ dữ liệu có kích thước lớn hoặc dữ liệu nhạy cảm. Dữ liệu nhị phân không dễ dàng bị thay đổi như JSON hoặc PlayerPrefs.

Ví dụ:
```csharp
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;
using UnityEngine;

[System.Serializable]
public class PlayerData
{
    public int health; // Biến lưu trữ sức khỏe
    public int score; // Biến lưu trữ điểm số
    public string currentScene; // Biến lưu trữ tên cảnh hiện tại
}

public class BinarySaveLoadManager : MonoBehaviour
{
    public PlayerData playerData; // Tham chiếu đến đối tượng PlayerData

    public void SaveData()
    {
        BinaryFormatter formatter = new BinaryFormatter(); // Tạo BinaryFormatter để chuyển đối tượng thành dữ liệu nhị phân
        string path = Application.persistentDataPath + "/playerData.dat"; // Đường dẫn đến file nhị phân
        FileStream stream = new FileStream(path, FileMode.Create); // Tạo hoặc ghi đè file

        formatter.Serialize(stream, playerData); // Chuyển đối tượng PlayerData thành dữ liệu nhị phân và ghi vào file
        stream.Close(); // Đóng file stream
    }

    public void LoadData()
    {
        string path = Application.persistentDataPath + "/playerData.dat"; // Đường dẫn đến file nhị phân
        if (File.Exists(path)) // Kiểm tra nếu file tồn tại
        {
            BinaryFormatter formatter = new BinaryFormatter(); // Tạo BinaryFormatter để đọc dữ liệu nhị phân
            FileStream stream = new FileStream(path, FileMode.Open); // Mở file để đọc

            playerData = formatter.Deserialize(stream) as PlayerData; // Đọc dữ liệu nhị phân và chuyển thành đối tượng PlayerData
            stream.Close(); // Đóng file stream
        }
    }
}

```
### Database (SQLite)
Đối với các ứng dụng cần lưu trữ dữ liệu phức tạp hoặc số lượng lớn dữ liệu, sử dụng cơ sở dữ liệu như SQLite là một lựa chọn tốt.

Ví dụ:
```csharp
using Mono.Data.Sqlite;
using System.Data;
using UnityEngine;

public class DatabaseManager : MonoBehaviour
{
    private string dbPath;

    void Start()
    {
        dbPath = "URI=file:" + Application.persistentDataPath + "/gameDatabase.db"; // Đường dẫn đến file cơ sở dữ liệu
        CreateDatabase(); // Gọi hàm tạo cơ sở dữ liệu
    }

    void CreateDatabase()
    {
        using (var connection = new SqliteConnection(dbPath)) // Mở kết nối đến cơ sở dữ liệu
        {
            connection.Open(); // Mở kết nối

            using (var command = connection.CreateCommand()) // Tạo một lệnh SQL
            {
                command.CommandText = "CREATE TABLE IF NOT EXISTS players (id INTEGER PRIMARY KEY, name TEXT, score INTEGER)"; // Lệnh tạo bảng
                command.ExecuteNonQuery(); // Thực thi lệnh
            }

            connection.Close(); // Đóng kết nối
        }
    }

    public void AddPlayer(string name, int score)
    {
        using (var connection = new SqliteConnection(dbPath)) // Mở kết nối đến cơ sở dữ liệu
        {
            connection.Open(); // Mở kết nối

            using (var command = connection.CreateCommand()) // Tạo một lệnh SQL
            {
                command.CommandText = "INSERT INTO players (name, score) VALUES (@name, @score)"; // Lệnh thêm một dòng vào bảng
                command.Parameters.AddWithValue("@name", name); // Thêm tham số name
                command.Parameters.AddWithValue("@score", score); // Thêm tham số score
                command.ExecuteNonQuery(); // Thực thi lệnh
            }

            connection.Close(); // Đóng kết nối
        }
    }

    public void GetPlayers()
    {
        using (var connection = new SqliteConnection(dbPath)) // Mở kết nối đến cơ sở dữ liệu
        {
            connection.Open(); // Mở kết nối

            using (var command = connection.CreateCommand()) // Tạo một lệnh SQL
            {
                command.CommandText = "SELECT * FROM players"; // Lệnh truy vấn tất cả các dòng từ bảng players

                using (IDataReader reader = command.ExecuteReader()) // Thực thi lệnh và đọc kết quả
                {
                    while (reader.Read()) // Đọc từng dòng kết quả
                    {
                        Debug.Log("ID: " + reader["id"] + " Name: " + reader["name"] + " Score: " + reader["score"]); // In ra thông tin của từng người chơi
                    }
                }
            }

            connection.Close(); // Đóng kết nối
        }
    }
}

```
### Lưu Scene và GameObject
Lưu và tải lại các Scene và GameObject cũng là một phần quan trọng trong việc quản lý dữ liệu trong Unity.

Ví dụ về lưu Scene:
```csharp
using UnityEngine;
using UnityEngine.SceneManagement;

public class SceneManagement : MonoBehaviour
{
    public void LoadNextScene()
    {
        int nextSceneIndex = SceneManager.GetActiveScene().buildIndex + 1; // Lấy chỉ số của cảnh tiếp theo
        if (nextSceneIndex < SceneManager.sceneCountInBuildSettings) // Kiểm tra nếu cảnh tiếp theo tồn tại
        {
            SceneManager.LoadScene(nextSceneIndex); // Tải cảnh tiếp theo
        }
    }

    public void RestartCurrentScene()
    {
        Scene currentScene = SceneManager.GetActiveScene(); // Lấy cảnh hiện tại
        SceneManager.LoadScene(currentScene.name); // Tải lại cảnh hiện tại
    }
}

```

Ví dụ về lưu GameObject:
```csharp
using UnityEngine;
using System.Collections.Generic;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

[System.Serializable]
public class GameObjectData
{
    public List<Vector3> positions = new List<Vector3>(); // Danh sách lưu trữ vị trí các đối tượng
    public List<string> names = new List<string>(); // Danh sách lưu trữ tên các đối tượng
}

public class GameObjectSaveLoad : MonoBehaviour
{
    public List<GameObject> gameObjects; // Danh sách các đối tượng cần lưu

    public void SaveGameObjects()
    {
        GameObjectData data = new GameObjectData(); // Tạo đối tượng GameObjectData

        foreach (var obj in gameObjects)
        {
            data.positions.Add(obj.transform.position); // Lưu vị trí của từng đối tượng
            data.names.Add(obj.name); // Lưu tên của từng đối tượng
        }

        BinaryFormatter formatter = new BinaryFormatter(); // Tạo BinaryFormatter
        string path = Application.persistentDataPath + "/gameObjects.dat"; // Đường dẫn đến file nhị phân
        FileStream stream = new FileStream(path, FileMode.Create); // Tạo hoặc ghi đè file

        formatter.Serialize(stream, data); // Chuyển đối tượng GameObjectData thành dữ liệu nhị phân và ghi vào file
        stream.Close(); // Đóng file stream
    }

    public void LoadGameObjects()
    {
        string path = Application.persistentDataPath + "/gameObjects.dat"; // Đường dẫn đến file nhị phân
        if (File.Exists(path)) // Kiểm tra nếu file tồn tại
        {
            BinaryFormatter formatter = new BinaryFormatter(); // Tạo BinaryFormatter
            FileStream stream = new FileStream(path, FileMode.Open); // Mở file để đọc

            GameObjectData data = formatter.Deserialize(stream) as GameObjectData; // Đọc dữ liệu nhị phân và chuyển thành đối tượng GameObjectData
            stream.Close(); // Đóng file stream

            for (int i = 0; i < gameObjects.Count; i++)
            {
                gameObjects[i].transform.position = data.positions[i]; // Đặt vị trí của từng đối tượng
                gameObjects[i].name = data.names[i]; // Đặt tên của từng đối tượng
            }
        }
    }
}

```
