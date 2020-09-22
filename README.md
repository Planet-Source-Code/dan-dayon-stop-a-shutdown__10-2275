<div align="center">

## Stop a Shutdown


</div>

### Description

This stops the system from shutting down when windows goes to shut down...
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Dan Dayon](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/dan-dayon.md)
**Level**          |Beginner
**User Rating**    |4.8 (29 globes from 6 users)
**Compatibility**  |VB\.NET
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__10-1.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/dan-dayon-stop-a-shutdown__10-2275/archive/master.zip)





### Source Code

```
'Constants
Private Const WM_QUERYENDSESSION As System.Int32 = &H11
Private Const WM_CANCELMODE As System.Int32 = &H1F
'And the Sub itself....
Protected Overrides Sub WndProc(ByRef m As Message)
	If m.Msg = WM_QUERYENDSESSION Then
'Check the m, if it's trying to shut down, don't send it. Send a new message cancelling it.
		Dim x As New Message
		x.Msg = WM_CANCELMODE
		MyBase.WndProc(x)
	Else
'Otherwise, just send the message.
		MyBase.WndProc(m)
	End If
End Sub
```

