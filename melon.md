[返回](./README.md)
>TreeNode*Param();//30 Param ::=	TypeName  FormList | VAR TypeName  FormList
{
    //新的声明语法树结点
    TreeNode* newNode=new TreeNode;
    newNode->lineno=input[pinput].lineshow;
    newNode->nodekind=7;
    newNode->idnum=0;
    string lex=input[pinput].lex,sem=input[pinput].sem;

*if((lex=="KEEPWORD"&&(sem=="10"|sem=="3"|sem=="15"|sem=="1"|sem=="21"))|lex=="ID"){*

**(newNode->attr).param=valparamtype;**
        ***TypeDef(newNode);***
        ~~FormList(newNode);~~
        return;
    }
*    else
*    pinput++;
*    return;
*}

---
```
void FormList(TreeNode* t);//31 FormList ::= ID  FidMore
{
    string lex=input[pinput].lex,sem=input[pinput].sem;
    if(lex=="ID"){
        (t->attr).name[]=sem;
        (t->attr).idnum++;
        match(lex,sem);
    }
    FidMore(t);
    return;
}
```
void FidMore(TreeNode* t);//32 FidMore	::=空| ,FormList
{
1.    string lex=input[pinput].lex,sem=input[pinput].sem;
2.   if(lex=="SCHAR"&&sem=="11"){
3.     if(lex=="SCHAR"&&sem=="6"){
       return;
        }
        else if(lex=="SCHAR"|sem=="13"){
            match("SCHAR","13);
            FormList(t);
        }
        else pinput++;
    }
4. return;
}
