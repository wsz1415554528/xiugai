# xiugai
xiu
#include<bits\stdc++.h>
#define MAXSIZE 100
using namespace std;

class student{
	private:
		char name[20];
		char sex;
		char proName[20];
		int proNum;
		char className[20];
		char phoneNum[20];
	public:
		double socre[20];
		double sumSocre;
		student() {
			
		}
		student getStuInformation(student d,int i) {
			cout << endl << "\t\t请输入第" << i << "个学生姓名：";
			cin >> d.name;
			cout << "\t\t请输入第" << i << "个学生性别，m为男，w为女：";
			cin >> d.sex;
			cout << "\t\t请输入第" << i << "个学生所参加的项目名称和编号：" << endl;
			cout << "\t\t项目名称：";
			cin >> d.proName;
			cout << "\t\t项目编号：";
			cin >> d.proNum;
			cout << "\t\t请输入第" << i << "个学生所在班级：";
			cin >> d.className;
			cout << "\t\t请输入第" << i << "个学生联系方式：";
			cin >> d.phoneNum;
			return d;
		}
		void showName(student d) {
			cout << d.name;
		}
		void showSocre(student d,int i) {
			cout << d.socre[i];
		}
		void operateSumSocre(student &d,int n) {
			int sum;
			for(int i = 0;i < n;i++) {
				d.sumSocre += d.socre[i];
			}
		}
		void sortPro(student d[],int n) {
			student temp;
			for(int i = 0;i < n;i++) {
				for(int j = i;j < n;j++) {
					if(d[i].proNum >= d[j].proNum) {
						temp = d[j];
						d[j] = d[i];
						d[i] = temp;
					}
				}
			}
		}
		void setStuInformation(student d) {
			cout << "\t\t姓名：" << d.name << endl;
			cout << "\t\t性别：" << d.sex << endl;
			cout << "\t\t班级：" << d.className << endl;
			cout << "\t\t联系方式" << d.phoneNum << endl; 
			cout << "\t\t所参加项目编号：" << d.proNum << endl;
			cout << "\t\t所参加项目名称：" << d.proName << endl;
			cout << "\t\t所得总分为：" << d.sumSocre << endl;
		}
};
