# makepen
* 대화 상자 기반
* 속성 옆의 대화상자에서 MK_MOUSEMOVE

## 코드
CPoint pnt;
#
void CPen7Dlg::OnMouseMove(UINT nFlags, CPoint point)
#
{
#
	if (nFlags == MK_LBUTTON) {
#
		CClientDC dc(this);
		#
		dc.MoveTo(pnt);
		#
		dc.LineTo(point);
		#
	}
	#
	pnt = point;
	#
	CDialogEx::OnMouseMove(nFlags, point);
	#
}
