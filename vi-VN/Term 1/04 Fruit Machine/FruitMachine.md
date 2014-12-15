---
title: Máy hoa quả
level: Cấp độ 2
stylesheet: scratch
language: en-GB
embeds: ""*.png""
note: ""notes for club leaders.md""
materials: ""*.sb2""
...

# Giới thiệu {.intro}
Đây là 1 trò chơi đơn giản có 3 hình họa để đổi trang phục. Bạn phải ngăn chúng lại khi chúng hiện ra hình ảnh giống nhau (giống 1 máy hoa quả!).

![screenshot](fruitmachine_screenshot.png)
>>>>>>> scratch2

# BƯỚC 1: Tạo 1 hình họa để đổi trang phục { .activity}

## Những việc cần làm { .check}

__Chúng ta hãy nhập những hình ảnh khác nhau cho trò chơi__

1. Bắt đầu 1 dự án scratch mới. Xóa bỏ hình con mèo bằg cách click vào đó sau đó click “Delete”
2. Đầu tiên, chúng ta hãy thêm 1 hình nền mới từ thư viện hình ảnh. Chọn hình nền  **rays** từ mục **Other** và sau đó xóa bỏ nền trắng ban đầu. 2. Bây giờ thêm 1 hình họa mới từ thư viện.
3. Chọn 1 hình ảnh từ bất kỳ thư mục nào. Chúng ta đã sử dụng **things/Bananas**, nhưng bạn có thể sử dụng bất kỳ hình ảnh nào bạn muốn.
4. Click vào màu xanh '**i**' bên cạnh hình ảnh của sprit trong cửa sổ Sprit, Đặt tên lại hình họa thành 'Fruit'.
5. Bây giờ click vào thẻ Trang phục và nhập thêm 2 loại nữa để có tất cả 3 trang phục (chúng ta đã dùng **things/apple** và **things/watermelon-a**, nhưng bạn có thể dùng bất cứ hình nào mình muốn).

__Bây giờ chúng ta có 1 số trang phục rồi, chúng ta muốn hình họa đổi các trang phục với nhau.__

# BƯỚC 2: Làm hình ảnh thay đổi { .activity}

## Những việc cần làm { .check}

1. Click vào thẻ `Scripts` {.blocklightgrey}.
2. Click vào `Events`{.blockgrey} và kéo 1 khối `when flag clicked` { .blockyellow} vào khu vực script.  Khi chúng ta click vào hình cờ màu xanh thì trò chơi bắt đầu.
3. Click vào thẻ Control, thêm 1 khối `forever` { .blockyellow} và kéo nó rồi thả xuống phần cuối.
4. Click vào hình cờ màu xanh **Click the green flag** ở góc trên bên phải. Lưu ý rằng có 1 đường viền màu vàng ở quan phần script. Nó đang chạy vì chúng ta đã click vào hình cờ xanh, nghĩa là khởi động trò chơi.  
5. Bây giờ click vào `Looks`{.blockgrey} và kéo thả vào phần `next costume` { .blockpurple}
6. Làm sao chúng ta có thể làm chậm tốc độ lại để nó không thay đổi quá nhanh? Click vào thẻ `Control`{.blockgrey} và kéo thả vào khối `wait 1 secs` { .blockyellow}
7. Điều chỉnh thời gian cho đến khi nó lặp lại ở nhịp độ nhanh hơn (đặt khoảng 0.5s là hợp lý). Điều gì sẽ xảy ra nếu chúng ta không có khối `wait 1 secs` { .blockyellow}?

```blocks
when FLAG clicked
forever    	
    next costume
    wait (0.5) secs
```

## Chạy thử chương trình { .flag}
__Click vào cờ màu xanh__
Trang phục có thay đổi ở 1 tốc độ hợp lý không?

## Lưu lại dự án { .save}

## Hãy thử { .try}

- Điều chỉnh thời gian ở khối `wait 1 secs` {.blockyellow}.
- Bạn nghĩ con số nào làm trò chơi trở nên quá dễ, hoặc quá khó?

# BƯỚC 3: Làm trò chơi dừng lại khi click vào đó {.activity}

## Những việc cần làm { .check}

**Tuyệt! Chúng ta có thể dùng hình họa thay đổi trang phục mãi mãi, nhưng làm sao chúng ta có thể khiến nó dừng lại khi click vào đó?**
Một cách để thực hiện điều này là sử dụng 1 biến số để đặt trạng thái của hình họa. Điều này sau này cũng sẽ rất hữu ích sau này...

- Tạo 1 biến số bằng cách click vào `Data` {.blockgrey} và `Make a variable`{.blocklightgrey}. Gọi là `stopped`{.blockorange} và chỉ dùng cho hình họa này, sau đó bỏ dấu tick ở hộp bên cạnh để nó không hiện trên màn hình nền nữa.
- Lúc bắt đầu trò chơi, hình họa sẽ không được click, vì thế chúng ta sẽ đặt biến số bằng với **""NO""**."
```blocks
when FLAG clicked
set [stopped v] to (NO)
forever
    next costume
    wait (0.1) secs
```
- Bây giờ chúng ta sẽ đặt biến số `stopped`{.blockorange} thành  **"YES"** khi click vào hình họa. 
```blocks
    when this sprite clicked
    set [stopped v] to (YES)
```
- Cuối cùng chúng ta cần làm cho hình họa ngừng đổi trang phục khi biến số `stopped`{.blockorange} đổi thành "YES". Thêm 1 vòng lặp `if...then` { .blockyellow} và sử dụng 1 khối điều hành  **equals** `[] = []` {.blockgreen} mới (ở bên dưới thẻ *Operators*) để kiểm tra xem `stopped`{.blockorange}  có phải vẫn là "NO" không.
```blocks
when FLAG clicked
set [stopped v] to (NO)
forever    
     if <(stopped) = [NO]> then
     next costume
     wait (0.5) secs
```

## Chạy thử chương trình { .flag}
__Click vào cờ màu xanh lá cây, đợi 1 chút, sau đó click vào hình họa__ 

- Nó có thay đổi trang phục trước khi click vào đó không?
- Nó có dừng lại khi click vào đó không?
- __Bắt đầu chương trình một lần nữa.__ Nó có dừng lại khi đặt con trỏ chuột trên đó mà không click không?
- Hình họa có dừng khi khi bạn click ở bất kỳ chỗ nào trên màn hình nền không?   

## Lưu lại dự án { .save}

# Bước 4: Tạo hình họa khác {.activity}
__Bây giờ chúng ta cần tạo những hình họa khác để có thể chơi trò chơi của chúng ta!__

## Những việc cần làm { .check }

1. **Nhân đôi hình họa** (trái cây) bằng cách click phải lên trên hình ở góc phải bên dưới.
2. Nhân đôi một hình họa lần nữa để có **3** hình họa trên màn hình.
3. Di chuyển mỗi hình họa để chúng cùng ở trên 1 đường thẳng. Chỉnh cho hình này nhỏ hơn nếu cần.

## Chạy thử chương trình { .flag}

__Click vào hình cờ màu xanh.__ Tất cả các hình họa nên thay đổi. Cố gắng dừng tất cả trên cùng 1 hình ảnh bằng cách click vào từng hình một!

## Lưu lại dự án { .save}

# Bước 5: Bắt đầu mỗi hình họa với 1 bộ trang phục bất kỳ { .activity}
__Chúng ta hãy dùng hình họa đổi thành 1 bộ trang phục bất kỳ khi click vào hình cờ xanh.__

Khi bắt đầu trò chơi ngay sau khi tải, tất cả các hình họa có cùng 1 trang phục và sau đó thay đổi theo liên kết.
Nếu chúng đổi trang phục theo cách khó đoán hơn, trò chơi sẽ trở nên thú vị (và khó hơn).

## Những việc cần làm { .check}

1. If you look under the `costumes`{.blocklightgrey}  tab for a sprite then you'll see that each costume has a number. You can specify which costume a sprite is wearing using either its name or its number.
2. To make the sprite start with a random costume, let's add a `switch costume to` { .blockpurple} block with  `pick random (1) to (3)` { .blockgreen} to choose 
the costume number. 
3. We can also use exactly the same block in the `forever`{.blockyellow} loop so that the sprite switches to a different costume each time it changes during the game.

```blocks
when FLAG clicked
set [stopped v] to (0)
switch costume to <pick random (1) to (3)>
forever	
	if <(stopped) = [NO]> then	
    	switch costume to <pick random (1) to (3)>
	     	wait (0.5) secs
```
4. Do the same thing for each of your sprites. 

## Test Your Project { .flag}
__Click the green flag.__ All the sprites should change their costumes in an unpredictable sequence.

How would we need to change our script if we added another costume?
 
## Save your project { .save}

##Things to try { .try}
 
 __Make the game harder__ 

Change the difficulty of the game somehow. Just making the costumes change quicker is fairly easy. Can you come up with something more imaginative. Some ideas you might like to try:

+ Change the number of costumes each sprite has.
+ Make some sprites have unique costumes.
+ Have different times between costume changes. 

__Have fun coming up with your own things!__

Every time you make a change, think about whether it makes the game easier or harder. Is the game too easy or too hard? How can you adjust the difficulty so it’s just right?

## Step 6: Display a message when the game has finished. { .activity}
__Let's show the player a "Game Over" message when they've finished__

## Activity Checklist { .check}

First of all, let's create a different Backdrop to display when the game has finished.
1. Click on the stage and then the `Backdrops`{.blocklightgrey} tab. Change the name of the existing backdrop to **"GameOn"**. 
2. Duplicate the backdrop and then add some text to the copy that says **"Game Over"**. You can change the size of the text by clicking on it and then 
dragging one of the corners. Rename this backdrop to be **"GameOver"**.
3. Click on the `Scripts`{.blocklightgrey} tab for the stage and set the "GameOn" backdrop to be the one displayed when the game is started. 	
4. How can we detect when all the sprites have stopped? Remember we use the `stopped`{.blockorange} variable to record whether each sprite has been clicked? Let's check the `stopped`{.blockorange} variable for the **Fruit3** sprite to see if the game is over.  Select the Fruit3 sprite and then can use a `x position of Fruit3` { .blockblue} block from the `Sensing`{.blocklightgrey} tab, but change **x position** to `stopped`{.blockorange}.
	
```blocks
when FLAG clicked
switch backdrop to [GameOn v]
forever
	if <([stopped v] of [Fruit3 v]) = [YES]> then
		switch backdrop to [GameOver v]
```

## Test Your Project { .flag}
__Click the green flag.__ Does the "Game Over" message appear when you click on Fruit3?

What happens if you stop Fruit3 before you've clicked on both of the other fruit sprites? Let's
modify our script so that it will work regardless of the order in which the sprites are stopped.

5. To check to see that __all three__ fruit sprites have had their `stopped`{.blockorange} variables set to **YES**, we can use the `and` {. blockgreen} operator. This is a compicated block that can be quite fiddly to assemble, so try and put it together one step at a time. 

```blocks
	when FLAG clicked
switch backdrop to [GameOn v]
forever
    if <<<([stopped v]  of [Fruit1 v]) = [YES]> and <([stopped v]  of [Fruit2 v]) = [YES]>> and <([stopped v]  of [Fruit3 v]) = [YES]>> then
        switch backdrop to [GameOver v]
```

## Test Your Project { .flag}
__Click the green flag.__ Does the "Game Over" message appear when you all 3 Fruits are stopped.
regardless of the order you clicked on them?

## Save your project { .save}

# Step 7. Tell the player whether they've won or lost. { .activity}

__The aim of the game is to click on the sprites so they stop while showing the same costume. It would be nice to also display a message that told you whether you'd won or lost.__

## Activity Checklist { .check}

1. We wrote the code to check that the game was over in __step 6__, so all we need to do now is check to see if the player has won. Go back to the backdrops and and add some more text to the GameOver backdrop so that also displays the word **"WIN"**. Then change its name to **"Win"**.
2. Copy the backdrop again to create one with a **"Lose"** message. Give it the name **"Lose"**.
3. Now we need some code to work out which backrop to display once the game is over. We can use an `if...then...else` { .blockyellow} block to see if the player has won or lost by comparing each `costume #`{.blockpurple}  (costume number) using a similar `x position of Sprite` { .blockblue} block like we did before. This time, instead of looking at the `stopped`{.blockorange} variable, we can check the`costume #`{.blockpurple}  and see if Fruit1 has the same costume as Fruit2, and if Fruit2 has the same costume as Fruit3.
 

```blocks
	when FLAG clicked
switch backdrop to [GameOn v]
forever
    if <<<([stopped v]  of [Fruit1 v]) = [1]> and <([stopped v]  of [Fruit2 v]) = [1]>> and <([stopped v]  of [Fruit3 v]) = [1]>> then
    	if <<([costume # v]  of [Fruit1 v]) = ([costume # v]  of [Fruit1 v])> and <([costume # v]  of [Fruit2 v]) = ([costume # v]  of [Fruit3 v])>> then
        	switch backdrop to [Win v]
        else    
			switch backdrop to [Lose v]
```
 
## Test Your Project { .flag}
__Click the green flag.__ Does the correct message appear when the game has finished? What will happen if each sprite's costume numbers don't match (for example, if Fruit2's costume number 3 is an apple and Fruit3's costume number 3 is a melon)?

## Save your project { .save}
   
__Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at this challenge!__

##Challenge: Make the game get harder and easier over time { .challenge}

Different people will have different skills at playing the game. __How could you make the game adjust its difficulty depending on the player?__

One way you could do it is to __adjust the speed the costumes change at__. You can use a variable, called `delay`{.blockorange}, to give the duration of each sprite’s wait block. If the player wins the round, the delay can be reduced a little (to make the game harder). If the player loses the round, the delay can be increased a little (to make the game easier). 

You'll probably need to think about using a different way of starting the game each time it is played instead of the `when flag clicked`{.blockyellow} Then you can store values in variables that are remembered between each round of the game. 

## Save your project { .save}

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
