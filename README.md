# hello-world
编程学习笔记



void unionL(List *La,list Lb)
{
    int La_len,Lb_len,i;
    ElemType e;
    la_len=ListLength(*La);
    La_len=ListLength(Lb);
    for(i=1;i<=Lb_len;i++)
    {
      GetElem(Lb,i,&e);
      if(!LocateElem(*La,e))
      {
          ListInsert(La,++La_len,e);
      }
}
}
