# verilog_mario

## Controll ( By AutoHotkey )
Because the "VeriLnstrument"(the verilog simulation software) only can controlled by mouse, but it's hard to complete that difficult 
operation. Therefore, it need a auxiliary software to help me tranfer from keyboard to mouse clicking.<br>
There are many software to do that. But in this project we are in winXP environment. So it's difficult to write by simply Python or C++ (not support by 32bits). But fortunately we have autohotkey, it has both 32bits & 64bits vision !! <br>
The following code is work on AutoHotKey<br>
```
x=500
y=500
r=50

w:: ;up
	while GetKeystate("w")
	{
		Click up
		MouseMove,x,y-r
		Click down
		Click up
	}	
	return
s:: ;down
	while GetKeystate("s")
	{
		Click up
		MouseMove,x,y
		Click down
		Click up
	}	
	return
a:: ;left
	while GetKeystate("a")
	{
		Click up	
		MouseMove,x-r,y
		Click down
		Click up	
	}
	return
d:: ;right
	while GetKeystate("d")
	{
		Click up	
		MouseMove,x+r,y
		Click down
		Click up	
	}
	return
p:: ;position
	MouseGetPos,x,y
```
Having this code, we can controll "w,s,a,d" as "up,down,left,right"<br><br>
AutoHotKey WinXP Version can download 
<a href="https://cn.allxpsoft.com/autohotkey-windows-xp/" target="_blank">here</a><br>


## Backgrounder Render ( By Excel VBA )
<img src="/picture/img_render.png" width="375" />

```
Sub render()
    For j = 1 To 281
         Worksheets(2).Cells(j, 1).Value = "16b'"
         For i = 16 To 1 Step -1
            If Worksheets(1).Cells(i, j).Interior.Color = RGB(255, 0, 0) Then
                Worksheets(2).Cells(j, 1).Value = Worksheets(2).Cells(j, 1).Value + "1"
            Else
                Worksheets(2).Cells(j, 1).Value = Worksheets(2).Cells(j, 1).Value + "0"
            End If
        Next i
    Next j
    Worksheets(2).Cells(1, 5).Value = Time()
End Sub

```
