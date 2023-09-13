#include <iostream>
#include <string>
using namespace std;
class FATHER {
 protected:
 string first_name;
 string surname;
 string dob;
 int bank_balance;
 public:
 FATHER(string fname, string sname, string d_o_b, int balance) {
 first_name = fname;
 surname = sname;
 dob = d_o_b;
 bank_balance = balance;
 }
void display_details() {
 cout << "Name: " << first_name << " " << surname << endl;
 cout << "DOB: " << dob << endl;
 cout << "Bank Balance: " << bank_balance << endl;
 }
};
class SON : public FATHER {
 public:
 SON(string fname, string sname, string sdob, int balance) : FATHER("", sname, "", balance) {
 first_name = fname;
 dob = sdob;
 }
 void display_details() {
 FATHER::display_details();
 cout << "Relation: SON" << endl;
 }
};
int main() {
 FATHER F1("John", "Doe", "01-01-1970", 50000);
 SON S1("David", "Doe", "01-01-2000", 10000);
 cout << "Father's Details:" << endl;
 F1.display_details();
 cout << endl << "Son's Details:" << endl;
 S1.display_details();
 return 0;
}
