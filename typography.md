---
layout: page
author: LeeKiJong
title: Study
Update: 2019-12-17
permalink: /Study/
main_nav: true
comments : true
---
<h2>스레드(멀티스레드)</h2>
하나의 프로세스에서 다시 여러 가지 일을 하는 것.  
Ex) 채팅 프로그램에서 파일 전송과 채팅이 동시에 되는 것.  
<h4>Runnable 인터페이스 구현을 통한 Thread</h4>
```java
ThreadTest threadTest = new ThreadTest();
Thread thread = new Thread(threadTest, "A")
thread.start();
```
```java
public class ThreadTest implements Runnable{
    public void run(){
      ....
    }
}
```
<h4>Thread 클래스 상속을 통한 Thread</h4>
```java
ThreadTest threadTest = new ThreadTest();
threadTest.setName("A")
threadTest.start();
```
```java
public class ThreadTest extends Thread{
    public void run(){
      ....
    }
}
```

<h4>멀티 쓰레드, 스레드2, 객체1</h4>
```java
ThreadTest threadTest = new ThreadTest();
Thread thread0 = new Thread(threadTest, "A")
Thread thread1 = new Thread(threadTest, "B")
thread0.start();
thread1.start();
```
```java
public class ThreadTest implements Runnable{
    public void run(){
      if(Thread.currentThread().getName().equals("A"))
        //조건 만드는 법
    }
}
```

<h4>멀티 쓰레드, 스레드2, 객체2</h4>
```java
ThreadTest threadTest0 = new ThreadTest();
ThreadTest threadTest1 = new ThreadTest();
Thread thread0 = new Thread(threadTest, "A")
Thread thread1 = new Thread(threadTest, "B")
thread0.start();
thread1.start();
```
```java
public class ThreadTest implements Runnable{
    public void run(){
      if(Thread.currentThread().getName().equals("A"))
        //조건 만드는 법
    }
}
```
<h4>synchronized</h4>
동기화  
스레드3, 객체1 형태로 했을 때 변수에 같이 접근 하기 때문에 인스턴스 값이 변경될 위험.  
해결법  
```java
public void run(){ // XXXXX
public synchronized void run(){ // XXXXX
```
<h2>JAVA 입출력</h2>
예외 처리문 필요
<h4>파일 출력</h4>
```java
InputStream is = new FileInputStream("경로"); //경로 쓸 때 특수문자는 앞에 한번 더 써주기 ex) \\
is.read(); //1byte씩 읽기
is.read(byte[]); //Byte[]씩 읽기
```

<h4>파일 입력</h4>
```java
OutputStream os = new FileOutputStream("경로"); //경로 쓸 때 특수문자는 앞에 한번 더 써주기 ex) \\
String str = "안녕하세요";
byte[] bs = str.getBytes();
os.write(bs);
```

<h4>파일 입출력</h4>
![1](https://user-images.githubusercontent.com/52438368/71395377-0a00f080-2659-11ea-91d3-3e41672c4d60.PNG)
![2](https://user-images.githubusercontent.com/52438368/71395378-0bcab400-2659-11ea-81b8-f6d0d0d42061.PNG)
<h4>DataInputStream, DataOutputStream</h4>
![3](https://user-images.githubusercontent.com/52438368/71395472-66fca680-2659-11ea-8891-8049ef4a258c.PNG)

<h2>깊이 우선 탐색</h2>
인접 리스트로 표현된 그래프: O(N+E)  
인접 행렬로 표현된 그래프: O(N^2)  
너비 우선 탐색보다 구현은 간단.


<h2>시간복잡도</h2>
<h4>버블 정렬</h4>
시간복잡도: O(n^2)  
제일 안좋다.
```java
 static void swap(int[] arry, int idx1, int idx2) {
        int tmp = arry[idx1];
        arry[idx1] = arry[idx2];
        arry[idx2] = tmp;
    }

    static void bublleSort(int[] arry, int n) {
        for (int i = 0; i < n - 1; i++) {
            for (int j = n - 1; j > i; j--)
                if (arry[j - 1] > arry[j]) {
                    swap(arry, j - 1, j);
                }
        }
    }
```
<h4>선택 정렬</h4>
시간복잡도: O(n^2)
```java
static void selectionSort(int[] array, int n) {
        for (int i = 0; i < n - 1; i++) {
            int min = i;
            for (int j = i + 1; j < n; j++) {
                if (array[j] < array[min])
                    min = j;
                swap(array, i, min);
            }
        }
    }
```
<h4>삽입 정렬</h4>
시간복잡도: O(n^2), 최선 O(n)
```java
static void insertionSort(int[] array, int n) {
    for (int i = 1; i < n; i++) {
        int j;
        int tmp = array[i];
        for (j = i; j > 0 && array[j - 1] > tmp; j--)
            array[j] = array[j - 1];
        array[j] = tmp;
    }
}
```

<h4>퀵 정렬</h4>
시간복잡도: O(nlogn), 최선 O(n^2), 최악 O(n^2)
```java
void quick_sort(int list[], int left, int right){
  if(left<right)
  {
    int q  = partition(list, left, right);
    quick_sort(list, left, q-1);
    quick_sort(list, q+1, right);
  }
}

int partition(int list[], int left, right){
  int pivot, temp;
  int low, high;
  low = left;
  high = right+1;
  pivot = list[left];
  do{
    do
    {
      low++;
    } while(low <=right && list[low] < pivot);
    do
    {
      high--;
    } while(high >= left && list[high] > pivot);
    if(low<high)
      swap(list[low], list[high]);
   } while(low<high);
   swap(list[left], list[high]);
   return high;
]
```

<h2>ArrayList, Vector</h2>
```java
int []array = {1, 2, 3};
ArrayList<Integer> list1 = new ArrayList<Integer>();
//값 넣기
for(int k:array){
  list1.add(k);
}
//원하는 위치에 값넣기
list1.add(0, 4);
//검색 찾기
if(list1.contatins(2)){
  System.out.println(list1.indexOf(2))//출력
}
//크기
list1.size();
```

<h2>Vector</h2>
```java
//ArrayList와 똑같음
//용량 구하는 함수는 벡터밖에없음
list1.capacity();
```

<h2>ArrayList, Vector 차이점</h2>
<h4>동기화</h4>  
Vector가 동기화 된다면 ArrayList는 동기화가 되지않은 상태입니다.  

쉽게말해 Vector는 한번에 하나의 스레드만 엑세스(접근) 가능하며, ArrayList는 동시에 여러 스레드가 작업할 수 있습니다.  

ArrayList에서 여러 스레드가 동시에 엑세스하는 경우 개발자가 명시적으로 동기화하는 코드를 추가해야합니다.  

<h4>스레드 안전</h4>  
스레드 안전이란 멀티 스레드 프로그래밍에서 여러 스레드가 동시에 접근이 이루어져도 프로그램 실행에 문제가 없음을 뜻합니다.  
앞서 말했듯이 Vector는 동기화가 되어있기 때문에 한번에 하나의 스레드만 접근할 수 있기때문에 스레드가 안전합니다.  

ArrayList는 동기화되지 않았기 때문에 명시적으로 동기화 할 필요가 있습니다.  


<h4>성능</h4>  
ArrayList는 동기화 되지않았기 때문에 동기화 된 벡터보다 더 빠릅니다.  

<h4>크기 증가</h4>  
Vector와 ArrayList 모두 동적 배열 클래스로 최대 인덱스를 초과할 때 추가되는 인덱스 수가 다릅니다.  

Vector는 현재 배열의 크기의 100%가 증가하며, ArrayList의 경우 현재 배열의 크기의 50%가 증가합니다.  

<h4>결론</h4>  

멀티스레드 환경이 아닌 경우 ArrayList를 사용하는 것이 좋다.  
Vector를 사용하라는 요구 사항이 없다면 ArrayList를 사용하자.  

<h2>Static</h2>
Static = 공유  
```java
public ㄴtatic int wallet = 200;  
```
지갑 공유 문제에서 사용
Static 있는 곳에는 주로 final을 사용함  
```java
public static final int i=1;
```
final = 상수, 변하지 않는 값
<h2>상속</h2>
```java
public class method1 extends 상속{
   public void method1(){
   // TODO....
   }
}
```

<h2>추상</h2>
Override 를 자동으로 생성해줌.
```java
public abstract class SuperClass{
  public SuperClass(){
  }
  public abstract void method1();
}
```

<h2>인터페이스</h2>  
<h4>정의</h4>
1. 객체의 소통 수단  
2. 작업 명세서  
3. JAVA에서 다형성을 가능하게 한다.  
4. 객체의 부속품화  

<h4>문법</h4>
1. 실제 기능은 없다. 구현된 기능은 없고 추상메소드와 상수만이 존재한다.  
2. private 안된다. 상수를 만들 때 Private 접근 제한자는 X  
3. 추상화 - 메소드는 무조건 추상 메소드만 존재한다.  
4. 객체타입 - 인터페이스는 개체는 아니다. 다만, 객체 타입으로만 사용된다.  
5. 구현은 실행 되는 객체의 메소드에서 한다.
```java
public interface InterfaceEx{
  public void inMethod();
}
```
```java
public class Ainterface implements InterfaceEx{
  public void inMethod(){
    System.out.println("AAAAA");
  }
}
```
```java
public class Binterface implements InterfaceEx{
  public void inMethod(){
    System.out.println("BBBBB");
  }
}
```

```java
public class Main {
  public static void main(){
    InterfaceEx Ainter = new Ainterface();
    InterfaceEx B inter = new Binterface();
    InterfaceEx[] inters = {Ainter, Binter};
    
    for(int i=0 ; i < inters.length ; i++){
      inters[i].inMethod();
    }
  }
}
```

배열로 만들어서 사용가능  
JAVA는 다중상속 X 대신에 다중구현(다형성) 가능  

<h2>인터페이스와 추상클래스</h2>  
<h4>공통점</h4>  
1. 추상메소드를 가지고있다. - 추상메소드를 가지고 있어 하위 클래스에서 구현해야 한다.  
2. 데이터 타입이 목적이다. - 객체생셩이 목적이 아니라 데이터 타입을 정의하는 것이 목적  
3. 객체 생성은 'anonymose'를 이용  
<h4>차이점</h4>  
1. 상속, 구현 - 추상메소드는 상속을 통한 사용이고, 인터페이스는 구현을 통한 사용이다.  
2. 구성요소 차이 - 추상클래스는 일반 클래스와 동일하게 변수, 메소드의 모든 기능을 사용할 수 있지만, 인터페이스는 상수와 추상메소드만이 존재한다.   
3. 단일상속, 다중구현 - 추상클래스는 단일 상속, 인터페이스는 다중구현 가능  

<h2>디자인 패턴</h2>  
1. 싱글턴 패턴  

```java
public class SingletonClass{
  private static SingletonClass SINGLETON_CLASS_INSTANCE = new singletonClass();
  public int i = 10;
  
  private SingletonClass(){
  }
  public static SingletonClass getSingletonClass(){
    if(SINGLETON_CLASS_INSTANCE == null){
      SINGLETON_CLASS_INSTANCE = new SingletonClass();
    }
    return SINGLETON_CLASS_INSTANCE;
  }
  public int geti(){
    return i;
  }
  public int seti(){
    this.i = i;
  }
}
```

<h2>API</h2>

사용 이유 : 다른 언어에 비해서 접하기 쉽고, 배우기 쉽다.  
개발자들이 편리하게 이용할 수 있는 풍부한 클래스들이 많다.
<h4>String API</h4>
String은 원래 기초데이터가 아니라 객체데이터지만 쓰는 경우가 많아서 기초데이터처럼 사용.   
str1.concat(str2): 문자열 연결  
str1.substring(3): 앞 3문자 자르고 출력  
str1.length(): 문자열 길이  
str1.toUpperCase(): 대문자로 만들기  
str1.toLowerCase(): 소문자로 만들기  
str1.charAt(3): 3번째 문자 출력  
str1.indexOf('C'): 특정 문자열의 위치  
str1.equlas(str2): 문자열 비교  
str1.trim(): 문자열 공백 제거(문자열 사이 공백은 무시, 문자열 첫 번째, 끝만 제거)  
str1.replace('a', 'z'):  a를 z로 바꾸기  
str1.replaceAll('abcd', 'zzzzzz'): 특정 문자열 변경  
메모리 과소비  
String클래스의 대안으로 StringBuffer, StringBuilder 등장(StringBuilder가 더 빠르다. 나머지는 동일)  
```java
StringBuilder sb = new StringBuilder("abcdefg");
sb.append("aaaaa"): 문자열 뒤에 붙이기
sb.insert(3, "AAA"): 3번째 인덱스부터 AAA 삽입
sb.delete(3, 5): 3번째 부터 5번째 까지 삭제
sb.deleteCharAt(10): 10번째 자리 삭제
```

<h4>날짜(Calendar) API</h4>
```java
Calendar calendar = Calender.getInstance();
int year = calendar.get(Calendar.YEAR);
int month = calendar.get(Calendar.MONTH)+1;
int day = calendar.get(Calendar.DAY_OF_MONTH);
int hour = calendar.get(Calendar.HOUR_OF_DAY);
int minute = calendar.get(Calendar.MINUTE);
int second = calendar.get(Calendar.SECOND);
```

<h4>속도 테스트 API</h4>
```java
System.currentTimeMillis();
```

<h4>Random 클래스</h4>
요즘은 Random클래스를 많이 이용한다.
```java
double d = Math.random();
```
```java
Random random = new Random();
random.nextInt(100);
```

<h4>Wrapper 클래스</h4>
기초데이터를 객체데이터로 변화시키는 클래스
```java
Integer integer = new Integer(10);
int i = integer.intValue();
```

<h4>Timer 클래스</h4>
```java
Timer timer = new timer(ture);
TimerTask t1 = new ExTimerTask1();
TimerTask t2 = new ExTimerTask2();

timer.schedule(t1, 2000)  //2초후 실행
timer.schedule(t2, 10000) //10초후 실행

Thread.sleep(11000);
```
```java
public class ExTimerTask1 extends TimerTask{
  public void run(){
    System.out.println("Task1의 작업 실행");
  }
}
```
<h4>StringTokenizer 클래스</h4>
문자열 나눌 때 중요

<h4>예외 처리</h4>
```java
try{

} catch(ArrayIndexOutOfBoundsException a){

} catch(NumberFormatException n){

} finally{
  System.out.println("finally는 무조건 실행된다.");
}
```
<h4>컬렉션(Collections)</h4>
컬렉션이란, 우리말로 쉽게 말해서 자료구조이다. 더 쉽게 말하면 배열.  

<h2>HashMap</h2>
```java
HashMap<Integer, String> hashmap = new HashMap<Integer, String>();
hashmap.put(0, "str0");
hashmap.get(2);
```

<h2>JAVA GUI</h2>
AWT 발전한 게 Swing
![4](https://user-images.githubusercontent.com/52438368/71397451-f3f72e00-2660-11ea-8a9b-4331031cd942.PNG)
<h4>버튼 만들기</h4>
```java
MakeBtn btn = new MakeBtn();
btn.setSize(new Dimension(200, 200));
btn.setVisible(true);
try{
  Thread.sleep(2000);
] catch(Exception e){}

btn.setVisible(false);
btn.dispose();   //자원 해제
```

```java
public class MakeBtn extends Frame{
  public MakeBtn(){
    Button btn = new Button("Button");
    add(btn);
  }
}
```

<h4>AWT(Frame, Panel, List, Components, Event)</h4>
```java
MakeFrame makeFrame = new MakeFrame();
makeFrame.setSize(new Dimension(500, 500));
makeFrame.setVisible(true);
```

```java
public class MakeFrame extends Frame implements ActionListener{
  private List list;
  private Panel panel;
  private TextField textField;
  private Button okBtn;
  private Button exitBtn;
  public MakeFrame(){
    list = new List();
    panel = new Panel();
    textField = new TextField(20);
    okBtn = new Button("OK");
    exitBtn = new Button("EXIT");
    
    setLayout(new BorderLayout());
    add(panel, BorderLayout.NORTH);
    add(list.BorderLayout.CENTER);
    
    panel.add(new Label("write"));
    panel.add(textField);
    panel.add(okBtn);
    panel.add(exitBtn);
    
    okBtn.addActionListener(this);
    exitBtn.addActionListener(this);
    
    addWindowListener(new WindowAdapter(){
      @Override
      public void windowClosing(WindowEvent e){
        setVisible(false);
        dispose();
        System.exit(0);
      }
    });
  }
  
  @Override
  public void actionPerformed(ActionEvent e){
    if(e.getSource() == okBtn){
      list.add(textField.getText());
    } else if(e.getSource() == exitBtn){
      setVisible(false);
        dispose();
        System.exit(0);
    }
  }
}
```

<h4>SWING</h4>
```java
MakeComp makeComp = new MakeComp();
makeComp.pack();
makeComp.setVisible(true);
```

```java
public class MakeComp extends JFrame implements ActionListener{
  JPanel jpanel;
  JLabel jLabel;
  JButton jButton;
  JButton jButtonExit;
  JTextField jTextField;
  JComboBow<String> jComboBox;
  JCheckBox jCheckBox;
  String[] items = {"A", "B", "C"};
  JLabel jLabelBlank;
  
  public MakeComp(){
    this.setDefaultCloseOperation(Frame.EXIT_ON_CLOSE);
  
    jPanel = (JPanel)getContentPane();
    jPanel.setLayout(new FlowLayout());
    jLabel = new JLabel("Label");
    jButton = new JBitton("Button");
    jTextField = new JTextField(20);
    jComboBox = new JComboBox<String>(items);
    jCheckBox = new JCheckBox("CheckBox");
    jLabelBlank = new JLabel();
    jButtonExit = new JButton("Exit");
    
    jPanel.add(jLabel);
    jPanel.add(jButton);
    jPanel.add(jTextField);
    jPanel.add(jComboBox);
    jPanel.add(jCheckBox);
    jPanel.add(jLabelBlank);
    jPanel.add(jButtonExit);
    
    jLabel.setPreferredSize(new Dimension(50, 50));
    jButton.setPreferredSize(new Dimension(100, 50));;
    jTextField.setPreferredSize(new Dimension(300, 50));
    jComboBox.setPreferredSize(new Dimension(50, 50));
    jCheckBox.setPreferredSize(new Dimension(100, 50));
    jLabelBlank.setPreferredSize(new Dimension(200, 50));
    jButtonExit.setPreferredSize(new Dimension(100, 50));
    
    jButton.addActionListener(this);
    jButtonExit.addActionListener(this);
    
  }
  
  @Override
  public void actionPerformed(ActionEvent e){
    if(e.getSource() == jButton){
      jLabelBlank.setText(jTextField.getText());
    } else if(e.getSource() == jButtonExit){
      setVisible(false);
        dispose();
        System.exit(0);
    }
  }
}
```
<h2>자바 네트워크</h2>
<h4>InetAddress 클래스</h4>
```java
InetAddress inetAddress = InetAddress.getByName(scanner.next());
System.out.println(inetAddress.getHostName());
System.out.println(inetAddress.getHostAddress());
```

<h4>URLConnection</h4>
URL 클래스: DNS를 통한 IP정보를 이용하여, URL객체를 만든 후 네트워크 접속 및 URL정보를 얻어 옵니다.  
URLConnection 클래스: 추상클래스로 URL객체로부터 생성 됩니다. URL클래스의 openConnection()메소드 이용.  
```java
String code = null;
Scanner scanner = new Scanner(System.in);
String address = scanner.next();

try{
  URL url = new URL(address);
  URLConnection con = url.openConnection();
  BufferedReader webData = new BufferedReader(new InputStreamReader(con.getInputStream()));
  FileWriter fw = new FileWriter("C:\\javalec\\workspace\\file.html", false);
  
  while((code = webData.readLine()) != null){
    fw.write(code);
  }
  fw.close();
  webData.close();
  
} catch(Exception e){}
```
<h4>Socket</h4>
: 네트워크 상에서 서로 다른 호스트 사이의 통신을 위한 수단.  
1) Server에서 ServerSocket을 만들고, 클라이언트의 요청을 기다림.  
2) Client에서 Socket을 만들고, I/O Stream을 만들어 Server로 요청을 함.  
3) SErver에서 Client의 요청을 받아 Socket을 만들고, I/O Stream을 만든다.
4) 통신함  
5) Socket 닫음. 

<h5>Server</h5>
```java
ServerSocket serverSocket = null;
Socket socket = null;
PrintWriter writer = null
BufferedReader reader = null;
String lineStr;

public MakeServerSocket(){
  try{
    serverSocket = new ServerSocket(2000);
    
    while(true){
      socket = serverSocket.accept();
      System.out.println("Client 요청");
      
      writer = new PrintWriter(socket.getOutputStream(), true);
      reader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
      
      while((lineStr = reader.readLine())!=null){
        writer.write(lineStr);
        System.out.println("input: " + lineStr);
      }
      writer.close();
      reader.close();
      socket.close();
    }
  } catch(Exception e){}
}
```

<h5>Client</h5>
```java
Socket socket = null;
PrintWriter writer = null;
BufferedReader reader = null;

public MakeClientSocket(){
  try{
    socket = new Socket("localhost", 2000);
    writer = new PrintWriter(socket.getOutputStream(), true);
    reader = new BufferedReader(new InputStreamReader(socket.getInputStream()));
    
    String str = null;
    BufferReader sReader = new BufferedReader(new BufferedReader(new InputStreamReader(System.in));
    
    while((str = sReader.readLine()) != null){
      write.println(str);
      System.out.println("output: " + str);
    }
    
    writer.close();
    reader.close();
    sReader.close();
    socket.close();
  } catch(Exception e){}
}

```






<h2>1. JAVA</h2>

JAVA는 네트워크상에서 쓸 수 있도록 미국의 선 마이크로 시스템즈가 개발한 객체 지향 프로그래밍 언어  

JAVA의 특징  

a. 자바가상머신(JVM)만 설치하면 컴퓨터의 운영체제에 상관없이 작동한다.(즉, 운영체제에 독립적)  

b. 기본 자료형을 제외한 모든 요소들이 객체로 표현  

c. 객체 지향 개념의 특징인 캡슐화, 상속, 다형성이 잘 적용된 언어  

d. Garbage Collector를 통한 자동적인 메모리 관리  

e. 멀티쓰레드(Multi-thread)를 지원  








<h2>2. OOP(객체지향 프로그래밍)</h2>

OOP란 Object-Oriented Programming의 약어로써 객체지향 프로그래밍을 의미  

데이터를 객체로 취급하여 프로그램에 반영한 것이며, 순차적으로 프로그램이 동작하는 기존의 것들과는  

다르게 객체와 객체의 상호작용을 통해 프로그램이 동작하는 것을 말한다.  

OOP 특징  

a. 객체지향 프로그래밍은 코드의 재사용성이 높다.  

b. 코드의 변경이 용이  

c. 직관적인 코드분석  

d. 개발속도 향상  

e. 상속을 통한 장점 극대화  





<h2>3. Object</h2>

Object(객체)는 OOP에서 데이터(변수)와 그 데이터에 관련되는 동작(함수). 즉 절차, 방법, 기능을 모두 포함한 개념  

예)기차역에서 승차권을 발매하는 경우, 실체인 '손님'과 동작인 '승차권 주문'은 하나의 객체이며, 실체인 '역무원'과  

동작인 '승차권 발매'도 하나의 객체이다.  

같은 성질, 같은 구조와 형태를 가지는 객체는 등급으로 정의하고 등급에 속하는 객체는 그 등급의 인스턴스라고 한다.  





<h2>4. Overloading vs Overriding ( 한번공부할때 확실히 차이를 알아둘 것, 평소에 알고 있어도 헷갈림)</h2>

Overloading(오버로딩)  

- 같은 이름의 메소드를 여러개 정의하는 것  

- 매개변수의 타입이 다르거나 개수가 달라야 한다.  

* return type과 접근 제어자는 영향을 주지 않음.  
ex)  
```java
OverLoding(int n){
  System.out.println("int " + n);
}
OverLoding(String s){
  System.out.println("String " + s);
}
```
이와 같이 넣는 값에 따라 결과가 다르게 나온다.

Overriding(오버라이딩)  

- 상속에서 나온 개념  

- 상위 클래스(부모 클래스)의 메소드를 하위 클래스(자식 클래스)에서 재정의  





<h2>5. Servlet, JSP</h2>

Servlet - Container가 이해할 수 있게 구성된 순수 자바 코드로만 이루어진 것(Html in JAVA), 다른 자바클래스에게 데이터 전달    
서블릿(servlet)은 서버에서 웹페이지 등을 동적으로 생성하거나 데이터 처리를 수행하기 위해 자바로 작성된 프로그램이다.   servlet은 Java코드 안에 HTML태그가 삽입되며 자바언어로 되어있다. .java가 확장자이다.  
 서블릿의 단어는 Server + Let의 합성어라고 알고 있는 사람도 있고 Server + Applet으로 알고 있는 사람도 있다.  
 사실 둘다 어려운 느낌이다. 하지만 쉽게 풀어보면 '클라이언트 요청을 처리하고 그 결과를 다시 클라이언트에게 전송하는   servlet 클래스의 구현 규칙을 지킨 자바프로그램'이라고 이해하면 좋을 듯하다.  
 서블릿(servlet)은 자바언어를 웹어플리케이션에 조금 더 개발하기 쉽게 하기 위해 만든 API(라이브러리, 클래스 들)이며   
 이 규약에 맞는 라이브러리나 클래스들을 상속 및 구현하여 만든 클래스들을 서블릿이라고 한다.  
 ~ 자바코드로 구현하고 컴파일하고 배포해야 한다.  
~ HTML태그로 문자열("")스크림으로 처리해야 한다.  
~ 코드가 수정되면 다시 컴파일하고 배포해야 한다.  
~ 웹에플리케이션 구조에서 사용자에게 결과를 보여주는 프리젠테이션 층을 담당  

JSP(Java Server Page) - html기반에 JAVA코드를 블록화하여 삽입한 것(JAVA in Html), 보여지는 부분    
HTML을 코딩하기 너무 어렵고 불편해서 HTML 내부에 Java코드를 삽입하는 형식이 JSP이다.  
다시 말해 서블릿의 단점을 보완하고자 만든 서블릿 기반의 스크립트 기술이다.  
서블릿을 이용하게 되면 웹프로그래밍을 할 수 있지만 자바에 대한 지식이 필요하며 화면 인터페이스 구현에 너무 많은 코드를 필요로 하는 등 비효율적인 측면들이 있다.  
때문에 서블릿을 작성하지 않고도 간편하게 웹프로그래밍을 구현하게 만든 기술이 JSP(Java Server Pages)이다.  
~ 키워드가 태그화 되어 서블릿에 비해 배우기 쉽다.  
~ 자바코드를 <%%>태그 안에 처리해주어야 한다.  
~ HTML처럼 태그를 사용하여 자바코드도 사용이 가능하다.  
~ 사용자의 요청을 받아 분석하고 비지니스 층과 통신하여 처리하고 처리한 결과를 다시 사용자에게 응답하는 컨트롤러 층을 담당   



<h2>6. JDBC</h2>

Java Data Base Connection의 약자로 JAVA 언어를 통해 SQL을 실행하기 위해 데이터 베이스를 연결해주는 응용프로그램 인터페이스를 의미  





<h2>7. Get과 Post 방식</h2>

Get 방식  

- 클라이언트에서 서버로 데이터를 전달할 때, 주소 뒤에 "이름"과 "값"이 결합된 스트링 형태로 전달  

- 주소창에 쿼리 스트링이 그대로 보여지기 때문에 보안성이 떨어진다.  

- 길이에 제한이 있다.(=전송 데이터의 한계가 있다.)  

- Post방식보다 상대적으로 전송 속도가 빠르다.  



Post 방식  

- 일정 크기 이상의 데이터를 보내야 할 때 사용한다.  

- 서버로 보내기 전에 인코딩하고, 전송 후 서버에서는 다시 디코딩 작업을 한다.  

- 주소창에 전송하는 데이터의 정보가 노출되지 않아 Get방식에 비해 보안성이 높다.  

- 속도가 Get방식보다 느리다.  

- 쿼리스트링(문자열) 데이터 뿐만 아니라, 라디오 버튼, 텍스트 박스 같은 객체들의 값도 전송가능.  



Get과 Post 차이점  

- Get은 주로 웹 브라우저가 웹 서버에 데이터를 요청할 때 사용  

- Post는 웹 브라우저가 웹 서버에 데이터를 전달하기 위해 사용.  

- Get을 사용하면 웹 브라우저에서 웹 서버로 전달되는 데이터가 인코딩되어 URL에 붙는다.  

- Post방식은 전달되는 데이터가 보이지 않는다.  

- Get방식은 전달되는 데이터가 255개의 문자를 초과하면 문제가 발생할 수 있다.  

- 웹서버에 많은 데이터를 전달하기 위해서는 Post 방식을 사용하는 것이 바람직하다.  





<h2>8. Session과 Cookie</h2>

Session과 Cookie 사용 이유

- 현재 우리가 인터넷에서 사용하고 있는 HTTP프로토콜은 연결 지향적인 성격을 버렸기 때문에 새로운 페이지를 요청할 때마다  

 새로운 접속이 이루어지며 이전 페이지와 현재 페이지 간의 관계가 지속되지 않는다. 이에 따라 HTTP프로토콜을 이용하게 되는   
 
 웹사이트에서는 웹페이지에 특정 방문자가 머무르고 있는 동안에 그 방문자의 상태를 지속시키기 위해 쿠키와 세션을 이용한다.  



Session  

- 특정 웹사이트에서 사용자가 머무르는 기간 또는 한 명의 사용자의 한번의 방문을 의미한다.  

- Session에 관련된 데이터는 Server에 저장된다.  

- 웹 브라우저의 캐시에 저장되어 브라우저가 닫히거나 서버에서 삭제시 사라진다.  

- Cookie에 비해 보안성이 좋다.  



Cookie  

- 사용자 정보를 유지할 수 없다는 HTTP의 한계를 극복할 수 있는 방법  

- 인터넷 웹 사이트의 방문 기록을 남겨 사용자와 웹 사이트 사이를 매개해 주는 정보이다.  

- Cookie는 인터넷 사용자가 특정 웹서버에 접속할 때, 생성되는 개인 아이디와 비밀번호, 방문한 사이트의 정보를 담은 임시 파일로써,  

  Server가 아닌 Client에 텍스트 파일로 저장되어 다음에 해당 웹서버를 찾을 경우 웹서버에서는 그가 누구인지 어떤 정보를 주로 찾았는지 등을 파악할 때 사용된다.


 
- Cookie는 Client PC에 저장되는 정보기 때문에, 다른 사용자에 의해서 임의로 변경이 가능하다.(정보 유출 가능, Session보다 보안성이 낮은 이유)



Q. 보안성이 낮은 Cookie 대신 Session을 사용하면 되는데 안하는 이유?

A. 모든 정보를 Session에 저장하면 Server의 메모리를 과도하게 사용하게 되어 Server에 무리가 감





<h2>9. MVC 패턴</h2>

MVC란?  

- 객체지향프로그래밍에서, MVC란 사용자 인터페이스를 성공적이며 효과적으로 데이터 모형에 관련 시키기 위한 방법론 또는 설계 방식중 하나이다. MVC방식은 자바, Smalltalk,  

- MVC 패턴은 목적 코드의 재사용에 유용한 것은 물론, 사용자 인터페이스와 응용프로그램 개발에 소요되는 시간을 현저하게 줄여주는 형식이라고 많은 개발자들이 평가하고 있다.  

MVC 구성요소  

Model - 소프트웨어 응용과 그와 관련된 고급 클래스 내의 논리적 데이터 기반 구조를 표현. 이 목적 모형은 사용자 인터페이스에 관한 어떠한 정보도 가지고 있지 않다.  

View - 사용자 인터페이스 내의 구성요소들을 표현(사용자에게 보여지는 화면)  

Controller - Model과 View를 연결하고 있는 클래스를 대표, Model과 View 내의 클래스들 간 정보 교환하는데 사용.  





<h2>10. Interface, Abstract</h2>

Interface  

- 일종의 추상 클래스  

- 오직 추상메서드와 상수만을 멤버로 갖는다.  

- Implements 키워드를 사용  

- 상속의 관계가 없는 클래스간 서로 공통되는 로직을 구현하여 쓸 수 있도록한다.  

- Extends는 하나의 클래스만 상속 가능하나 Interface는 다중 상속이 가능하다.  

Abstract  

- 추상메서드를 하나 이상 가진 클래스  

- 자신의 생성자로 객체 생성 불가능  

- 하위 클래스를 참조하여 상위 클래스의 객체를 생성  

- 하위 클래스를 제어하기 위해 사용  



Interface vs Abstract  

공통점   

- new 연산자로 인스턴스 생성 불가능.  

- 프로토타입만 있는 메서드를 갖는다.  

- 사용하기 위해서는 하위클래스에서 확장/구현 해야 한다.  

차이점  

- 사용하는 키워드가 다르다.  

- Abstract는 일반 메서드를 사용할 수 있지만, Interface는 메서드 선언만 가능하다.  





<h2>11. Call by Reference, Call by Value</h2>

Call by Reference - 매개 변수의 원래 주소에 값을 저장하는 방식. 클래스 객체를 인수로 전달한 경우  

Call by Value - 인수로 기본 데이터형을 사용. 주어진 값을 복사하여 처리하는 방식. 메서드 내의 처리 결과는 메서드 밖의 변수에 영향을 미치지 않는다.  





<h2>12. Static의 의미</h2>   
- 클래스가 로딩될 때, 메모리 공간을 할당하는데 처음 설정된 메모리 공간이 변하지 않음을 의미  

- 객체를 아무리 많이 만들어도 해당 변수는 하나만 존재(객체와 무관한 키워드)  





<h2>13. Framework</h2>
- 특정 형태의 소프트웨어 문제를 해결하기 위해 상호 협력하는 클래스프레임과 인터페이스 프레임의 집합  
- 특정한 틀을 만들어놓고 거기에 살을 붙여 놓음으로써 프로그램을 만들어 작업시간을 줄여주는 것이다.   
- 프레임워크는 특정 개념들의 추상화를 제공하는 여러 클래스나 컴포넌트로 구성된다.  
- 프레임워크는 이렇게 추상적인 개념들이 문제를 해결하기 위해 같이 작업하는 방법을 정의한다.  
- 프레임워크 컴포넌트 들은 재사용이 가능하다.  
- 프레임워크는 좀 더 높은 수준에서 패턴을 조작한다.  
* 프레임워크가 중요한 이유는 객체지향 개발을 하게 되면서 개발자의 취향에 따라 다양한 프로그램이 나오게 되었다.  
 프로그램 개발에 투입되는 개발자도 점점 늘어남에 따라 전체 시스템의 통합성, 일관성이 부족하게 되었기 때문이다.   
 그래서 개발자의 자유를 제한하기 위해 프레임워크를 도입했다.  

프레임워크가 가져야할 특징  
a. 개발자들이 따라야할 가이드라인을 가진다.  
b. 개발할 수 있는 범위가 정해져 있다.  
c. 개발자를 위한 다양한 도구들이 지원된다.  

프레임워크의 장/단점  
장점 - 개발 시간을 줄일 수 있고 오류로부터 자유로울 수 있다.  
단점 - 프레임워크에 너무 의존하면 개발 능력이 떨어져서 프레임워크 없이 개발하는 것이 불가능해지는 점이다.  


<h2>14. Garbage Collection(가비지 컬렉션)</h2>  

시스템에서 더이상 사용하지 않는 동적 할당된 메로리 블럭을 찾아 자동으로 다시 사용 가능한 자원으로 회수하는 것으로   

시스템에서 가비지컬렉션을 수행하는 부분을 가비지 컬렉터라 부른다.  
```java
public class Main {
    public static void main(String[] args) {
        String url = "https://";
        url += "LeeKiJong.github.io";
        System.out.println(url);
    }
}
```
url이 가리키고 있던 힙의 "https://" 부분은 삭제 되고 url은 "https://LeeKiJong.github.io" 가 된다.  




<h2>15. Primitive type과 Reference type</h2>

Primitive type - 변수에 값 자체를 저장   

정수형 byte, short, int, long  

실수형 float, double  

문자형 char  

논리형 boolean  

* Primitive type은 Wrapper Class를 통해 객체로 변형할 수 있다.  

예) int→Integer, char→Character(int와 char를 제외한 Primitive type의 다른 자료형들은 맨 앞 알파벳을 대문자로 바꿔주면 된다. float→Float)  

Reference type - 메모리상에 객체가 있는 위치를 저장  

종류 - Class, Interface, Array 등  





<h2>16. Wrapper Class</h2>

Primitive type으로 표현할 수 있는 간단한 데이터를 객체로 만들어야 할 경우가 있는데 그러한 기능을 지원하는 클래스





<h2>17. Spring Framework(스프링 프레임워크)</h2>

자바(JAVA) 플랫폼을 위한 오픈소스(Open Source) 애플리케이션 프레임워크(Framework)  

자바 엔터프라이즈 개발을 편하게 해주는 오픈 소스 경량급 애플리케이션 프레임워크  

자바 개발을 위한 프레임워크로 종속 객체를 생성해주고,  조립해주는 도구  

자바로 된 프레임워크로 자바SE로 된 자바 객체(POJO)를 자바EE에 의존적이지 않게 연결해주는 역할  

스프링 특징 간단히  

- 크기와 부하의 측면에서 경량.  

- 제어 역행(IoC)이라는 기술을 통해 애플리케이션의 느슨한 결합을 도모  

- 관점지향 프로그래밍(AOP)을 위한 풍부한 지원  

- 애플리케이션 객체의 생명 주기와 설정을 포함하고 관리한다는 점에서 일종의 컨테이너(Container)라고 할 수 있음  

- 간단한 컴포넌트로 복잡한 애플리케이션을 구성하고 설정할 수 있음  

스프링 특징 자세히  

a. 경량 컨테이너로서 자바 객체를 직접 관리.  

   각각의 객체 생성, 소멸과 같은 라이프 사이클을 관리하며 스프링으로부터 필요한 객체를 얻어올 수 있다.  

b. 스프링은 POJO(Plain Old Java Object) 방식의 프레임워크.  

   일반적인 J2EE 프레임워크에 비해 구현을 위해 특정한 인터페이스를 구현하거나 상속을 받을 필요가 없어 기존에   

   존재하는 라이브러리 등을 지원하기에 용이하고 객체가 가볍다.  

c. 스프링은 제어의 역행(IoC : Inversion of Control)을 지원.  

   컨트롤의 제어권이 사용자가 아니라 프레임워크에 있어서 필요에 따라 스프링에서 사용자의 코드를 호출한다.  

d. 스프링은 의존성 주입(DI : Dependency Injection)을 지원  

   각각의 계층이나 서비스들 간에 의존성이 존재할 경우 프레임워크가 서로 연결시켜준다.  

e. 스프링은 관점 지향 프로그래밍(AOP : Aspect-Oriented Programming)을 지원  

   따라서 트랜잭션이나 로깅, 보안과 같이 여러 모듈에서 공통적으로 사용하는 기능의 경우 해당 기능을 분리하여 관리할 수 있다.  

f. 스프링은 영속성과 관련된 다양한 서비스를 지원  

   iBatis나 Hibernate 등 이미 완성도가 높은 데이터베이스 처리 라이브러리와 연결할 수 있는 인터페이스를 제공한다.  

g. 스프링은 확장성이 높음.  

   스프링 프레임워크에 통합하기 위해 간단하게 기존 라이브러리를 감싸는 정도로 스프링에서 사용이 가능하기 때문에 수많은 라이브러리가   

   이미 스프링에서 지원되고 있고 스프링에서 사용되는 라이브러리를 별도로 분리하기도 용이하다.  





<h2>18. Thread</h2>

Thread(쓰레드) - 프로세스내에서 동시에 실행되는 독립적인 실행 단위를 말함, 장점으로는 자원을 많이 사용하지 않고 구현이 쉬우며 범용성이 높다.  

Process(프로세스) - 운영체제에서 실행중인 하나의 프로그램(하나 이상의 쓰레드를 포함한다.)  

Thread 장점  

- 빠른 프로세스 생성  

- 적은 메모리 사용  

- 쉬운 정보 공유  

Thread 단점  

- 교착상태에 빠질 수 있다.  

* 교착상태 - 다중프로그래밍 체제에서 하나 또는 그 이상의 프로세스가 수행 할 수 없는 어떤 특정시간을 기다리고 있는 상태.  

Thread와 Process 차이  

여러 분야에서 '과정' 또는 '처리'라는 뜻으로 사용되는 용어로 컴퓨터 분야에서는 '실행중인 프로그램'이라는 뜻으로 쓰인다.   

이 프로세스 내에서 실행되는 각각의 일을 스레드라고 한다. 프로세스 내에서 실행되는 세부 작업 단위로 여러 개의 스레드가 하나의 프로세스를 이루게 되는 것이다.  





<h2>19. 접근제한자(public > protected > default > private)</h2>

public - 접근 제한이 없다.(같은 프로젝트 내에 어디서든 사용가능)  

protected - 같은 패키지 내, 다른 패키지에서 상속받아 자손클래스에서 접근 가능   

default - 같은 패키지 내에서만 접근 가능  

private - 같은 클래스 내에서만 접근 가능  



<h2>20. 소켓 통신(TCP/UDP)</h2>

TCP(Transmission Control Protocol)  

- 연결형 서비스 제공  

- 높은 신뢰성 보장  

- 연결의 설정(3-way handshaking)  

- 연결의 해제(4-way handshaking)  

- 데이터 흐름 제어, 혼잡 제어  

- 전이중, 점대점 서비스(양방향 송수신 서비스)  

UDP(User Datagram Protocol)  

- 비연결형 서비스 제공  

- 신뢰성이 낮음  

- 데이터의 전송 순서가 바뀔 수 있음  

- 데이터 수신 여부 확인 안함(3-way handshaking과 같은 과정 X)  

- TCP보다 전송속도가 빠름  



<h2>21. Stack, Queue</h2>

STACK  

- LIFO(Last In First Out)의 후입선출 구조  

- push();를 이용한 데이터 입력, pop();을 이용한 데이터 출력  

- 예) 시스템 스택 : 함수의 호출과 복귀 순서는 스택의 구조를 응용하여 관리  

- 역순 문자열 만들기, 수식의 괄호 검사, 수식의 후위 표기법 변환  

- 자바에서는 스택 대신에 덱(deque)를 사용하기도 함

QUEUE  

- FIFO(First In First Out)의 선입선출 구조  

- enQueue();를 이용한 데이터 입력, deQueue();를 이용한 데이터 출력  

- 예) 우선순위가 같은 작업 예약(인쇄 대기열), 선입선출이 필요한 대기열(티켓 카운터)  

* Linear Queue(선형큐)는 메모리 재사용이 불가능 이러한 문제점을 보완하여 Circular Queue(원형 큐)가 나옴  





<h2>22. Singleton Design Patter(싱글톤 디자인 패턴, 싱글톤 패턴)</h2>

- 클래스 인스턴스가 하나만 만들어지도록 하고, 그 인스턴스에 대한 전역 접근을 제공한다.

<h2>23. Strategy Pattern(스트레티지 패턴)</h2>

- 알고리즘 군을 정의하고 각각을 캡슐화하여 교환해서 사용할 수 있도록 만든다.  
스트레티지를 활용하면 알고리즘을 사용하는 클라이언트와는 독립적으로 알고리즘을 변경할 수 있다.  
어떤 객체를 만들 때 객체가 가지는 기능들이 다양하게 존재한다. 이러한 기능들을 추상화 하여 언제든지 적용할 수 있게 만드는 것.  
기능을 부품화.



<h2>24. Database에서 Index란?</h2>

인덱스는 데이터베이스 분야에 있어서 테이블에 대한 동작의 속도를 높여주는 자료 구조를 일컫는다.  

인덱스는 테이블 내의 1개의 컬럼, 혹은 여러 개의 컬럼을 이용하여 생성될 수 있다.  

고속의 검색 동작뿐만 아니라 레코드 접근과 관련 효율적인 순서 매김 동작에 대한 기초를 제공한다.  

인덱스를 저장하는 데 필요한 디스크 공간은 보통 테이블을 저장하는 데 필요한 디스크 공간보다 작다.  

데이터베이스에서 테이블과 클러스터에 연관되어 독립적인 저장 공간을 보유하고 있는 객체(object)이다.   

사용자는 데이터베이스에 저장된 자료를 더욱 빠르게 조회하기 위하여 인덱스를 생성하고 사용한다.   


DB에서 자료를 검색하는 두 가지 방법  

FTS(Full Table Scan) : 테이블을 처음 부터 끝까지 검색하는 방법  

Index Scan : 인덱스를 검색하여 해당 자료의 테이블을 액세스 하는 방법.  

<h2>자바 관련 사이트</h2>
![5](https://user-images.githubusercontent.com/52438368/71399779-1a6c9780-2668-11ea-9e11-d59e57d1ace0.PNG)





