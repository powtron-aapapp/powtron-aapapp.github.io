### 在 Markdown 文件中、使用 Mermaid

只需使用 **三重反引號**（```）括住 Mermaid 語句，即可讓文件呈現圖表、具備視覺化效果。

````markdown
```mermaid

    %%Mermaid code

```
````

### 繪製流程圖

生成一個從左到右排列、A 指向 B、B 指向 C、C 指向的流程圖。

```mermaid
graph LR;
    A-->B;
    B-->C;
    C-->D;
```

```markdown
graph LR;
    A-->B;
    B-->C;
    C-->D;
```

### 增加標籤與樣式

如果想要增加連結的標籤，可以使用 `|文字|` 來註解。

```mermaid
graph LR;
    A-->|連結1|B;
    B-->|連結2|C;
    C-->|連結3|D;
```

```markdown
graph LR;
    A-->|連結1|B;
    B-->|連結2|C;
    C-->|連結3|D;
```

### 使用不同形狀

可以使用 `style` 設定節點的樣式，圖表可以包含：

- `("文字")` 代表橢圓形
- `{"文字"}` 代表菱形
- `["文字"]` 代表矩形

```mermaid
graph LR;
style A fill:#f9f,stroke:#333,stroke-width:2px;
style B fill:#ff0,stroke:#333,stroke-width:2px;

    A("開始") --> B{"條件判斷"};
    B -->|是| C["執行動作"];
    B -->|否| D[結束];
```

```markdown
graph LR;
style A fill:#f9f,stroke:#333,stroke-width:2px;
style B fill:#ff0,stroke:#333,stroke-width:2px;

    A("開始") --> B{"條件判斷"};
    B -->|是| C["執行動作"];
    B -->|否| D[結束];
```

### 也可由上至下繪製

使用 graph LR;（由左到右）、或 graph TD;（由上到下）來繪製流程圖。

```mermaid
flowchart TD
    A[Christmas] -->|Get money| B(Go shopping)
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[fa:fa-car Car]
```

```markdown
flowchart TD
    A[Christmas] -->|Get money| B(Go shopping)
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[fa:fa-car Car]
```

### 序列圖（Sequence Diagram）

```mermaid
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: I feel great!
```

```markdown
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: I feel great!
```

### 甘特圖（Gantt Chart）

```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```

```markdown
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```

### 類別圖（Class Diagram）

```mermaid
classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
      +String beakColor
      +swim()
      +quack()
    }
    class Fish{
      -int sizeInFeet
      -canEat()
    }
    class Zebra{
      +bool is_wild
      +run()
    }
```

```markdown
classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
      +String beakColor
      +swim()
      +quack()
    }
    class Fish{
      -int sizeInFeet
      -canEat()
    }
    class Zebra{
      +bool is_wild
      +run()
    }
```

### 狀態圖（State Diagram）

```mermaid
stateDiagram
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

```markdown
stateDiagram-v2
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

### 餅圖（Pie Chart）

```mermaid
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

```markdown
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

### ER 圖（ER Chart）

```mermaid
erDiagram
    CUSTOMER }|..|{ DELIVERY-ADDRESS : has
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER ||--o{ INVOICE : "liable for"
    DELIVERY-ADDRESS ||--o{ ORDER : receives
    INVOICE ||--|{ ORDER : covers
    ORDER ||--|{ ORDER-ITEM : includes
    PRODUCT-CATEGORY ||--|{ PRODUCT : contains
    PRODUCT ||--o{ ORDER-ITEM : "ordered in"
```

```markdown
erDiagram
    CUSTOMER }|..|{ DELIVERY-ADDRESS : has
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER ||--o{ INVOICE : "liable for"
    DELIVERY-ADDRESS ||--o{ ORDER : receives
    INVOICE ||--|{ ORDER : covers
    ORDER ||--|{ ORDER-ITEM : includes
    PRODUCT-CATEGORY ||--|{ PRODUCT : contains
    PRODUCT ||--o{ ORDER-ITEM : "ordered in"
```

## Flowchart

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

## Sequence diagram

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Some note
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

## Gantt diagram

```mermaid
gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram to mermaid
excludes weekdays 2014-01-10

section A section
Completed task            :done,    des1, 2014-01-06,2014-01-08
Active task               :active,  des2, 2014-01-09, 3d
Future task               :         des3, after des2, 5d
Future task2               :         des4, after des3, 5d
```

## Class diagram (experimental)

```mermaid
classDiagram
Class01 <|-- AveryLongClass : Cool
Class03 *-- Class04
Class05 o-- Class06
Class07 .. Class08
Class09 --> C2 : Where am i?
Class09 --* C3
Class09 --|> Class07
Class07 : equals()
Class07 : Object[] elementData
Class01 : size()
Class01 : int chimp
Class01 : int gorilla
Class08 <--> C2: Cool label
```

```mermaid

flowchart LR

A{藍芽連線}
B{#91;*IDN?#93;<br>與 Inverter 連線}
C{#91;暫時停止判斷#93;<br>P1_2 == 0<br>&<br>P3_5 == 0}
D[至設定畫面頁<br>暫時停止按鈕顯示於ON位置]
E{#91;退出暫時停止#93;<br>設定 P_3 = 1}
F[Do anything]
G[異常停止]
H[正常<br>開始輪詢]

%%N[fa:fa-car Car]
%%J(Go shopping)
%% 使用圓角矩形
%%P[inverter連線]
%%H[Crash]
%% style P fill:#f9c2ff,stroke:#333,stroke-width:2px;

A --> |OK|B  
A --> |NG|G   
B --> |NG| C
B --> |OK| H
C --> |Yes|D
C --> |No|G  
D --> E
E --> |Yes|B
E --> |No|F
F --> |至設定畫面頁|D
F --> F

```

```mermaid
flowchart LR

B((輸出)) 
C{P1_2 == 0}
D["#91;外部供電#93;<br>OUTOFF = 1<br>P1_3 = 0"]
E["#91;未供電#93;<br>OUTOFF = 1"]
F(停止輸出)

B-->|暫時停止| C
C-->|Yes| D
C-->|No| E
D-->F
E-->F

G(停止輸出)
H{P1_2 == 0}
I["#91;外部供電#93;<br>OUTOFF = 0<br>P1_3 = 1"]
J["#91;未供電#93;<br>OUTOFF = 0"]
K(輸出)

G-->|恢復輸出| H
H-->|Yes| I
H-->|No| J
I-->K
J-->K
```
