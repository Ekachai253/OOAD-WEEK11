###นายเอกชัย  ภมรสุขนิรันดิ์ 57030253
# OOAD-WEEK11
##State Diagram
#ข้อ 1 รับโทรศัพท์
```
[*] -r-> Phone: not working
Phone -r-> Vibrator : Incoming Call
Vibrator -r-> AnswerThePhone : Waiting for areply
AnswerThePhone --> HangUp
Vibrator --> NoAnswer
NoAnswer -r-> HangUp
HangUp --> [*]
HangUp --> Phone
```
![](http://www.plantuml.com/plantuml/img/YzQALT0jqhLJ2CZ8pqkrKiZBBr4epo_ApinBvm8BGMJ3CfEA4aloYnIi53ppalDpWT8ApeavELnm2R0onxpYyjIYa8nKY5OhXV34p1AGsZIWYiIYr8ASIYuqDRf0RHw9UUcX1KXc0SNyyY4AkM0CY0rGfH0Ah31QAnQP2pOL0000)
#ข้อ 2 ตู้เติมเงินโทรศัพท์
```
[*] -r-> stanby 
stanby -r-> working : insert coin
working -r-> SendData : enter number
SendData --> ShowOK : right
ShowOK --> [*] : Power down
ShowOK --> stanby
```
![](http://www.plantuml.com/plantuml/img/YzQALT0jqhLJA2v9p4kgLE22qc2nyloYxCoyT0KhXSoyujIY4eNa_CmyBfWeM4bmQbwAIs998b1DQbv9Qf52NcbkKceH5rnS5wGe8x_Stnkef2WpFQE42ye5oKG3hRTI2CWl1-fCoI_FGvQ3k0G0)
#ข้อ 3 เปิดโน๊ตบุ๊ค
```
[*] -r-> notebook : not working
notebook -r-> working : Power up
working -r-> receiveDirective : select program
receiveDirective -r-> processProgram
processProgram --> outputProgram
outputProgram --> working : Oprn New Program
outputProgram --> notebook : OFF Program
notebook --> [*]
```
![](http://www.plantuml.com/plantuml/img/TSyz3eCm30NWFQVmZ9GBT62g684TCL1aeOWsZfo4NBzknAzGj-VdBrBS5JrerYLO2lWYck7nYv28PsCdjTSPhQsObX8oHAUsAkyPHpGBFes4846WnxTaS4mJ3nzr4_cTR4VqlbtHTGGjWc9mCMpWCkNzyRF6iOKQ4_p7frkRgjhXSQkOhkY_)
#ข้อ 4 ตู้ATM
```
[*] -r-> stanby 
stanby -r-> working : put card
working -r-> sendDATA : enterPIN
sendDATA -r-> receiveDATA
receiveDATA -r-> agree
agree --> [*] : Power down
agree --> stanby
```
![](http://www.plantuml.com/plantuml/img/YzQALT0jqhLJA2v9p4kgLE22qc2nyloYxCoyT0KhXOBI4eNanA8KBfWGH4zgNegBOuWZK45gNabgKO2d7nTS3AoYA3KvDRCi5IJ0XSI6I2Qc5wMcSe591LqWFnhe5Yk5WFpor2A5bFpoF2GfYAi0)
#ข้อ 5
```
[*] -r-> stanby 
stanby -r-> working : insert coin
working -r-> catch_a_toy : Control to play
catch_a_toy --> getToy
getToy --> [*]
working -r-> toy_not_catch : control to play
toy_not_catch --> [*]
toy_not_catch --> stanby
getToy --> stanby
```
![](http://www.plantuml.com/plantuml/img/POyn2e0m34NtdYApq0iuk7W5Dv5IYzHYIQG6fBUtj0fLfmylBpzaR2QGGNPmiCOvWhWpivF2vj122mwF9J0OSYWUcXMZsQnAAwQOj9wG0tbWWjthAEgfJBPTUA0eIcGoDjExCAaAYLLUJPNcK_cUFnL_MlweJnLo0G00)

##Activity Diagram 

#ข้อ 1 เปิดพัดลม
```
(*) --> plug in?
if "plug in" then
-->  open fan
else 
--> [No plug] piug in 
--> open fan
--> off fan
--> (*)
```
![](http://www.plantuml.com/plantuml/img/qz3ILD3LjLCeo2bDLyZCi-VAJ5DGWdAK54eoKlEuGD8A-GMfUGffYNbSgJd5gGfWiMY_VB2sM8M2JB1wY31S9PYJbWPdQsXf0W00)
#ข้อ 2 รถเเท็กเส้น taking robot
```
(*) --> powerUP
powerUP--> check line
if "real" then
--> LeftAndRight
LeftAndRight --> MoterMove
MoterMove --> powerDown
else 
--> [false]NotMoterMove
NotMoterMove --> powerDown
powerDown --> (*)

```
![](http://www.plantuml.com/plantuml/img/qz3ILD3LjLCeo2zFBGeDu8BI8A7aZDJaR8MSpBnKhimq1QMYrCGS9OMIZDGyBf2iJsfQYMDUIb1cUaO95p87R9nlVabgaMz-MIeNd8MmnYM_F8yhDQSuLG5iKdHQ8f0TwvTVWj25p47J26U1nJMqDBa0)
#ข้อ 3 longin garena
```
(*) --> OpenProgram
---> EnterPassword
if "Password Accept" then
--> UseProgram
else
--> [Password Not Accept] EnterPassword
if "" then
--> [Yes]UseProgram
else 
--> [No] logout
--> (*)
```
![](http://www.plantuml.com/plantuml/img/qz3ILD3LjLFmBqZD2oZAJozApENI1GcuvfMa5WKa5XUNvnUbS6McAIZ1E0gEoScf1ILA2YKPgNbS8BMXnQamlQavnQbWiMYuSh_y4gYMM2oc8XaJ7PbQ78jcbW94nYy_LY4dFps_j0JCrz3I1000)
#ข้อ 4 เช็คสินค้าในร้านค้า
```
(*) --> OpenAShop
--> CheckGoods
if""then
--> [Exist] Remove the Product to Sale
--> ProductSell
else
--> [out fo Stock] Order a Purchase
--> CheckGoods
ProductSell --> (*)
```
![](http://www.plantuml.com/plantuml/img/JOv12eCm54Jtdc9mfO9NA9HIkbIQfRW8oPU8gL-IdzBZrwOkNCxZCJDLKwDjB-WsMg_AyLRyqisHMHxCDXRpL9RYQCryk7_cA2EUzE8tOUVe0zja1C9GsbFM3gR8-u9y_CE1as3QBM6pZEY2fG2DFWNZzE6STayT-M3Lr5y0)
#ข้อ 5 รับโทรศัพท์
```
(*) --> Phone
--> IncomingCall
if""then
--> [blank] Answer the Phone
--> talk
--> (*)
else
--> [busy] IncomingCall
```
![](http://www.plantuml.com/plantuml/img/qz3ILD3LjLC8oCZFI-K2iJppalDpC_FIdHDpShWoqvIKIZ9Iyy0oqKavYNdPiGgEUSNbgKKAG74aRIM9ETbWXeQM9bTgJd4gL4jfSMKiYfa0)
