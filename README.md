#include<iostream>
using namespace std;
struct student
{
	char name[50];
	char num[20];
	int age;
	struct student *next;
};
int main()
{
	struct student *p,*q,*head;
	int s;
	head=new student;
	q=head;
	p=q;
	cout<<"输入姓名:"<<endl<<"输入学号:"<<endl<<"输入年龄:"<<endl;
	cin>>p->name;
	cin>>p->num;
	cin>>p->age;
	while(cout<<"1or2"<<endl<<"1 继续"<<endl<<"2 停止"<<endl,cin>>s,s==1)
	{
		p=new student;
		q->next=p;
		q=p;
		cin>>p->name;
		cin>>p->num;
		cin>>p->age;
		p->next=NULL;
	}
	
	p=head;
	while(p!=NULL)
	{
		cout<<"姓名:"<<p->name<<endl<<"学号:"<<p->num<<endl<<"年龄:"<<p->age<<endl;
		p=p->next;
	}
	p=head;
	do
	{
		q=p->next;
		delete p;
		p=q;
	}while(q);
}
