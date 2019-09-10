# makepen
* 대화 상자 기반
* 속성 옆의 대화상자에서 MK_MOUSEMOVE

## 코드_01
CPoint pnt;  
void CPen7Dlg::OnMouseMove(UINT nFlags, CPoint point)  
{  
	if (nFlags == MK_LBUTTON) {  
		CClientDC dc(this);  
		dc.MoveTo(pnt);  
		dc.LineTo(point);  
	}  
	pnt = point;  
	CDialogEx::OnMouseMove(nFlags, point);  
}
## 코드_02
void CPen7Dlg::OnMouseMove(UINT nFlags, CPoint point)  
{  
	if (nFlags == MK_LBUTTON) {  
		CClientDC dc(this);  
		CPen pen(PS_SOLID, 32, RGB(0, 0, 255));  
		//크기,색상  
		dc.SelectObject(&pen);  
		dc.MoveTo(pnt);  
		dc.LineTo(point);  
	}  
	pnt = point;  
	CDialogEx::OnMouseMove(nFlags, point);  
}  
CPoint pnt는 Pen7Dlg.h라는 헤더파일의 class 안의  
public:  
	afx_msg void OnMouseMove(UINT nFlags, CPoint point);  
	CPoint pnt;//헤더파일의 선언을 통해 사용 가능  
에 선언
