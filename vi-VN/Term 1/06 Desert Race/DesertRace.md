---
title: Desert Race
level: Level 2
language: en-GB
stylesheet: scratch
embeds: "*.png"
note: "notes for club leaders.md"
materials: "*.sb2"
...

# Lời giới thiệu { .intro}
Trò chơi dành cho 2 người chơi này là cuộc đua giữa một chú vẹt và một cô sư tử trên sa mạc. Mỗi người chơi phải ấn một phím nhanh nhất có thể để di chuyển con thú của họ, con thú đầu tiên chạm tới cạnh của màn hình sẽ chiến thắng.

![screenshot](desertrace_screenshot.png)

# BƯỚC 1: Tạo khung cảnh và thêm các hoạ tiết { .activity}

## Danh sách liệt kê hoạt động { .check}
>>>>>>> scratch2

1. Chọn sân khấu và thêm bối cảnh **Nature/desert** (Tự nhiên/sa mạc). Đánh dấu vào các ô bên dưới: 
2. Thêm một đồ họa mới, chọn hình ảnh **Lioness** (cô sư tử) trong tệp **Animals**. 
3. Thêm một đồ họa khác, chọn hình ảnh **Parrot** (chú vẹt) trong tệp **Animals**. `Shrink`{.blocklightgrey} để nó có kích thước tương tự cô nàng sư tử.


# BƯỚC 2: Làm cho chú khỉ và cô sư tử di chuyển { .activity}

Chúng ta cần làm cho hoạt họa di chuyển khi bạn ấn phím.

## Việc cần làm { .check}


1. Trước tiên hãy chọn hình ảnh sư tử và đặt nó vào `move (4) steps`{.blockblue} khi bạn ấn phím **‘L’**

```blocks
when [l v] key pressed
    move (4) steps
```

2. Tiếp theo, chọn hình chú vẹt và đặt nó vào `move (4) steps`{.blockblue} khi bạn ấn phím **‘A’** .

```blocks
when [a v] key pressed
    move (4) steps
```


## Chạy thử dự án của bạn { .flag}
__Click vào lá cờ màu xanh lá__ 
Liệu cô nàng sư tử và chú vẹt của bạn có di chuyển trên màn hình khi bạn ấn phím ‘A’ và ‘L’?

## Lưu dự án của bạn { .save}

# BƯỚC 3: Bắt đầu cuộc đua { .activity}

Chúng ta cần có một cách để bắt đầu cuộc đua và biết được người chiến thắng.
__Đầu tiên chúng ta tạo một nút khởi động.__

## Những việc cần làm { .check}


1. Thêm một hình họa mới từ một file.. Chọn hình họa **button3** ở bên trong phần **“Things”**.
2. Chỉnh sửa nút hình họa, thêm từ **‘start’** (bắt đầu) vào đó và click "OK". Di chuyển hình ảnh đến giữa sân khấu.
3. Hãy bắt đầu thêm một dòng lệnh cho hình hoạ biết khi nào dự án được khởi động:

```blocks
    when FLAG clicked
    show
```

4. Bây giờ chúng ta cần nút đếm ngược từ 3, sau đó nói "Go" (bắt đầu đua) và `hide`{.blockblue} khi nó được click. Thêm một dòng lệnh khác như dưới đây:

```blocks
when this sprite clicked
    say [3] for (1) secs
    say [2] for (1) secs
    say [2] for (1) secs
    say [GO!] for (1) secs
    hide
```


##Chạy thử dự án của bạn { .flag}
__Click vào lá cờ màu xanh lá.__ 

Khi bạn nhấn nút khởi động, nó có đếm ngược để bắt đầu cuộc đua trước khi biến mất không?

## Lưu dự án của bạn { .save}



Chúng ta cần để cho các tay đua di chuyển sau khi cuộc đua bắt đầu và biết rằng khi nào cuộc đua kết thúc. Bởi vậy, chúng ta cần một biến để lưu giữ thông tin đó.

1. Thêm một biến cho tất cả các hình họa gọi là `racing`{.blockorange}. Bỏ chọn ô cạnh đó để nó không thể hiển thị trên sân khấu.
2. Bây giờ hãy thiết lập **racing** về **0** khi dự án khởi động lần đầu tiên. Thay đổi dòng lệnh `when flag clicked`{.blockyellow} trước đó để được như sau: 

```blocks
when FLAG clicked
    show
    set [racing v] to (0)
```


3. Tiếp theo, thiết lập biến **racing** tới 1 khi đồng hồ đếm ngược kết thúc.
4. Bây giờ, chúng ta cần dừng cô sư tử và chú vẹt lại trừ khi biến của cuộc đua là 1. Click vào hình chú vẹt. __Thêm một khối điều khiển vào chương trình__ mà chỉ cho phép chú vẹt di chuyển khi __racing = 1__.

```blocks

    when [a v] key pressed
    if <(racing) = [1]>
        move (4) steps
```
5. Làm tương tự với hình họa của cô nàng sư tử.


## Chạy thử dự án của bạn { .flag}
__Click vào lá cờ màu xanh lá.__ 

Cô sư tử và chú vẹt chỉ di chuyển sau khi dừng đém ngược phải không?

Chúng ta cần biết người dành chiến thắng trong cuộc đua và đặt lại nó khi kết thúc để có thể đua một lần nữa.

## Lưu dự án của bạn { .save}

# BƯỚC 4: Kết thúc cuộc đua { .activity}

## Danh sách liệt kê hoạt động { .check}

1. Thêm một khối lệnh cho chú vẹt để đặt biến **racing** trở về 0 khi hình họa chạm tới góc của màn hình.

```blocks
when [a v] key pressed
if <(racing) = [1]>
    move (4) steps
    if <touching [edge v]?>
    set (racing) to [0]
```


2. Giờ đây chúng ta cần chú vẹt cho ta biết nếu nó chiến thắng cuộc đua. Ghi lại một âm thanh mới cho hình họa chú vẹt, nó sẽ được phát khi chú vẹt chiến thắng. Click `sounds`{.blocklightgrey}  và sau đó ghi lại âm thanh của chú vẹt chiến thắng trong cuộc đua!

3. Thêm khối lệnh âm thanh `play`{.blockpurple} mà bạn ghi lại được và sau đó để cho chú vẹt nói rằng nó đã chiến thắng:

```blocks
    when [a v] key pressed
    if <(racing) = [1]>
        move (4) steps
        if <touching [edge v]?>
            set (racing) to [0]
            play sound [recording1 v]
            say [The Parrot Wins! v] for (3) secs   
```

4. Bây giờ hãy lặp lại các bước trên đối với cô sư tử. 

##Chạy thử dự án của bạn { .flag}
__Click vào lá cờ màu xanh lá.__ 

Bạn có thể nhấn nút bắt đầu và tiếp tục cuộc đua bằng cách ấn phím ‘A’ và ‘L’ không?
Liệu hình họa có phát ra âm thanh chiến thắng khi nó hoàn thành cuộc đua?

##Lưu dự án của bạn { .save}

# BƯỚC 5: Đặt lại trò chơi { .activity}

Sau khi cuộc đua kết thúc, chúng ta cần cho những hình họa biết chúng ta đã chiến thắng và đặt lại trò chơi để có thể chơi một lần nữa.

__Chúng ta cần hình họa chiến thắng truyền tin rằng nó đã giành phần thắng.__

## Những việc cần làm { .check}


1. Click vào hình họa chú vẹt.
Thêm một khối lệnh truyền tin cho một tin nhắn **"finished”** sau khi hình họa thông báo rằng nó đã chiến thắng.

```blocks
when [a v] key pressed
if <(racing) = [1]>
    move (4) steps
    if <touching [edge v]?>
        set (racing) to [0]
        play sound [recording1 v]
        say [The Parrot Wins! v] for (3) secs
        broadcast [finished v]
```


2. Bây giờ, chúng ta cần thêm một dòng lệnh mới để lắng nghe tín hiệu kết thúc và di chuyển chú vẹt trở về vị trí khởi động. Chuyện gì xảy ra khi ta thay đổi giá trị **x** được thiết lập?


```blocks
when I receive [finished v]
    set x to (-170)
```

3. Thêm lệnh tương tự cho cô sư tử. Kiểm tra các giá trị **x** khác nhau để chắc rằng cô sử tử và chú vẹt thẳng hàng tại vị trí khởi động.
4. Chúng ta cũng cần phải đặt cô sư tử và chú vẹt ở vị cùng vị trí khi dự án bắt đầu chạy. Do đó, thêm một dòng lệnh khác cho mỗi con vật để di chuyển chúng về vị trí khởi động khi click vào lá cờ.


```blocks
when FLAG clicked
    set x to (-170)
```

5. Bây giờ click vào nút “Sprite” và thêm dòng lệnh để biết khi nó nhận được tin nhắn đã hoàn thành.



##Chạy thử dự án của bạn { .flag}

__Click vào lá cờ màu xanh lá.__ 

Bạn có thể đua với một người bạn, một trong hai bạn di chuyển con vẹt bằng cách ấn phím ‘A’ còn người còn lại di chuyển cô sư tử bằng phím ‘L’ không?


##Lưu dự án của bạn { .save}


##Thử thách 1: Thêm một động cơ tăng tốc { .challenge}



* __Thử thêm một động cơ tăng tốc__ mà ta có thể dùng một lần trong mỗi cuộc đua giúp chú vẹt và cô sư tử __30 bước trong một lần.__
* __Thêm một trang phục mới__ cùng với tia lửa phía sau mỗi hình họa sẽ xuất hiện khi nhấn nút tăng tốc.
* __Thêm một âm thanh khác__ để hình họa sẽ phát ra khi tăng tốc.

```blocks
when [p v] key pressed
if <<(racing) = [1]> and <(boosted) = [0]>>
    switch to costume [parrot-boost v]
    set [boosted v] to [1]     
    move (4) steps
    if <touching [edge v]?>
         set (racing) to [0]
        play sound [recording1 v]
        say [The Parrot Wins! v] for (3) secs
        broadcast [finished v]
```


##Chạy thử dự án của bạn { .flag}

##Lưu dự án của bạn { .save}

##Thử thách 2: Dùng custom blocks để đơn giản hóa dòng lệnh { .challenge}


Dòng lệnh để kiểm tra nếu cuộc đua kết thúc giờ đây được sử dụng trong hai nơi cho mỗi hình họa: khi hình họa di chuyển bình thường, và khi chúng tăng tốc. Chúng ta có thể đơn giản hóa dòng lệnh của mình bằng cách dùng custom block, đó chính là một phần của dòng lệnh giúp ta có thể dùng chúng nhiều hơn một điểm, cũng giống như việc viết Scratch code block!

1. Chọn dòng lệnh của chú vẹt.
2. Chọn bảng màu `More Blocks`{.blocklightgrey} và sau đó click vào `Make a Block`{.blocklightgrey}.
3. Đặt tên cho khối custom bằng cách gõ **"finished"** vào ô màu hồng, sau đó chọn OK.
4. Ta có thể thấy khối `define finished`{.blockpurple} xuất hiện trong cửa sổ dòng lệnh. Kéo nó ra một vùng trống.
5. Gỡ khối `if`{.blockyellow}`touching edge?`{.blocklightblue}`then`{.blockyellow} và kéo nó tới khối `define finished`{.blockpurple}

```blocks
define finished
 if <touching [edge v]?>
     set (racing) to [0]
     play sound [recording1 v]
     say [The Parrot Wins! v] for (3) secs
     broadcast [finished v]

when [q v] key pressed 
if <<(racing) = [1]> and <(boosted) = [0]>>
    switch to costume [parrot-boost v]
    set [boosted v] to [1]     
    move (4) steps
finished
```

Bạn có thể kéo khối `finished`{.blockpurple} từ bảng màu và dùng nó như những mục mã hóa khác?

Xóa khối `if`{.blockyellow}`touching edge?`{.blocklightblue} khác từ dòng lệnh và thay thế nó bằng một khối `finished`{.blockpurple} tự tạo.

Liệu nó có thể làm cho chương trình của bạn dễ đọc hơn không? Bạn có thể tạo một khối tự tạo tương tự cho hình họa cô sư tử không?

##Chạy thử dự án của bạn { .flag}

##Lưu dự án của bạn { .save}

__Rất tốt, bạn đã hoàn thành, giờ hãy tận hưởng trò chơi của mình nào!__
