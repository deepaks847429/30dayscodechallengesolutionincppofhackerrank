# 30dayscodechallengesolutionincppofhackerrank
day 0

#include <iostream>
#include <algorithm>
using namespace std;
int main(){
    string input_string;
    getline(cin, input_string);
    cout<<"Hello, World."<<endl;
    cout<<input_string<<endl;
    return 0;
}
    
    day 1
    #include <iostream>
#include <iomanip>
#include <limits>

using namespace std;

int main() {
    int i = 4;
    double d = 4.0;
    string s = "HackerRank ";
    int n;
    double m;
    string s1;
    cin>>n;
    cin>>m;
    getline(cin>>ws,s1);
    cout<<(i+n)<<endl;
    cout<<fixed<<setprecision(1)<<(d+m)<<endl;
    cout<<(s+s1)<<endl;
    
    return 0;
    
    day 2
    #include<bits/stdc++.h>
using namespace std;

    int main()
    {
        double meal_cost;
        cin>>meal_cost;
        int tip_percent;
        cin>>tip_percent;
        int tax_percent;
        cin>>tax_percent;
        double tip=meal_cost*tip_percent/100;
        double tax=meal_cost*tax_percent/100;
        double totalcost=meal_cost+tip+tax;
        cout<<round(totalcost);
        
        return 0;
    }
    day 3
    
    #include <bits/stdc++.h>

using namespace std;
int main(){
    int n;
    cin>>n;
    if(n%2==0){
        if(n>=2 &&n<=5){
            cout<<"Not Weird";
        }
        else if(n>=6 && n<=20){
            cout<<"Weird";
        }
        else{
            cout<<"Not Weird";
        }
        
    }
    else{
        cout<<"Weird";
    }
    return 0;
}
               day 4
  #include <iostream>
using namespace std;
class Person {
public:
    int age;

    Person(int initialAge);

    void amIOld();

    void yearPasses();
};
Person::Person(int initialAge) 
{
    // Add some more code to run some checks on initialAge
    if (initialAge > 0) age = initialAge;
    else 
    {
        cout << "Age is not valid, setting age to 0." << endl;
        age = 0;
    }
}

void Person::amIOld() 
{
    // Do some computations in here and print out the correct statement to the console
    if (age < 13) cout << "You are young." << endl;
    else if (age < 18) cout << "You are a teenager." << endl;
    else cout << "You are old." << endl;
}

void Person::yearPasses() 
{
    // Increment the age of the person in here
    age++;
}

int main(){
    int t;
	int age;
    cin >> t;
    for(int i=0; i < t; i++) {
    	cin >> age;
        Person p(age);
        p.amIOld();
        for(int j=0; j < 3; j++) {
        	p.yearPasses(); 
        }
        p.amIOld();
      
		cout << '\n';
    }

    return 0;}
                day 5
     #include<iostream>
using namespace std;
int main(){
    int n;
    cin>>n;
    for(int i=1;i<=10;i++){
        cout << n << " x " << i << " = " << n * i <<endl;
    }
    return 0;
}
                         day 6
  #include <iostream>
using namespace std;
    int main() {
    int x;
    cin >> x;
    for(int i = 0; i < x; i++){
        string s;
        string s1, s2;
        cin >> s;
        for(int j=0; j < s.size(); j++){
            if(j%2==0){
                s1 += s[j];
            }else{
                s2+= s[j];
            }
        }
        cout << s1 << " " << s2 << endl;
    }
    return 0;

}
                                       day 7
                                       
   #include <bits/stdc++.h>

using namespace std;


int main(){
    int n;
    cin >> n;
    vector<int> arr(n);
    for(int arr_i = 0;arr_i < n;arr_i++){
       cin >> arr[arr_i];
    }
    
    for(int arr_i = n-1;arr_i >= 0;arr_i--){
       cout << arr[arr_i] << " ";
    }
    cout << endl;
    return 0;
}         
                day 8
    #include<iostream>
#include <map>
using namespace std;
int main() {
    int x;
    cin >> x;
    map<string, string> all;
    for(int i = 0; i < x; ++i){
        string s, p;
        cin >> s >> p;
        all[s] = p;
    }
    string h;
    while(cin >> h){
        if(all.find(h) == all.end()){
            cout << "Not found" << endl;
        }
        else{
            cout << h << "=" << all.at(h) << endl;
        }
    }
    return 0;
}
    day 9
    #include <bits/stdc++.h>

using namespace std;
    int factorial(int n){
    int r;
    if(n != 1){
        r = n * factorial(n-1);
    }
    else
        r = 1;
    return r;
}

int main() {
    int n;
    cin >> n;
    int r = factorial(n);
    cout << r << endl;
    return 0;
}
      day 10
    #include <bits/stdc++.h>

using namespace std;

    int main()
{
    int n,count=0,max=0;
    cin >> n;

    while(n)
    {
        if (n&1)
            count++;
        else 
            count = 0;
        if (max < count)
            max = count;
        n>>=1;
    }
    cout << max;

    return 0;
}
      day 11
    #include <bits/stdc++.h>

using namespace std;

int add(int arr[6][6], int arr_i, int arr_j){
    int sum = arr[arr_i][arr_j];
    sum += arr[arr_i][arr_j +1];
    sum += arr[arr_i][arr_j +2];
    sum += arr[arr_i +1][arr_j +1];
    sum += arr[arr_i +2][arr_j];
    sum += arr[arr_i +2][arr_j +1];
    sum += arr[arr_i +2][arr_j +2];
    return sum;
}

int main(){
    int sum = -9 * 7;
    int arr[6][6];
    for(int arr_i = 0;arr_i < 6;arr_i++){
       for(int arr_j = 0;arr_j < 6;arr_j++){
          cin >> arr[arr_i][arr_j];
       }
    }
    for(int arr_i  = 0;arr_i < 4;arr_i++){
        for(int arr_j  = 0;arr_j < 4;arr_j++){
            int t = add(arr, arr_i, arr_j);
            if(t > sum)
                sum = t;
        }
    }
    cout << sum << endl;
    return 0;
}
      day 12
    #include <iostream>
#include <vector>

using namespace std;


class Person{
	protected:
		string firstName;
		string lastName;
		int id;
	public:
		Person(string firstName, string lastName, int identification){
			this->firstName = firstName;
			this->lastName = lastName;
			this->id = identification;
		}
		void printPerson(){
			cout<< "Name: "<< lastName << ", "<< firstName <<"\nID: "<< id << "\n"; 
		}
	
};
class Student :  public Person{
    private:
        vector<int> testScores;  
    public:
          // Write your constructor
        Student (
            string firstName_,
            string lastName_,
            int identification_,
            vector<int> testScores_
        ) :
            Person(firstName_, lastName_, identification_),
            testScores(testScores_)
        {
            
        }
                       
          // Write char calculate()
        char
        calculate (
            void
        ) {
            char letterGrade = '?';
            float average = 0.0;
            
            // Calculate average
            for (auto & score : testScores) {
                average += score;
            }
            average /= testScores.size();
            
            // Assign letter grade
            if (average >= 90.0) {
                letterGrade = 'O';
            } else if (average >= 80.0) {
                letterGrade = 'E';
            } else if (average >= 70.0) {
                letterGrade = 'A';
            } else if (average >= 55.0) {
                letterGrade = 'P';
            } else if (average >= 40.0) {
                letterGrade = 'D';
            } else {
                letterGrade = 'T';
            }
            
            return letterGrade;
        }
};
int main() {
	string firstName;
  	string lastName;
	int id;
  	int numScores;
	cin >> firstName >> lastName >> id >> numScores;
  	vector<int> scores;
  	for(int i = 0; i < numScores; i++){
	  	int tmpScore;
	  	cin >> tmpScore;
		scores.push_back(tmpScore);
	}
	Student* s = new Student(firstName, lastName, id, scores);
	s->printPerson();
	cout << "Grade: " << s->calculate() << "\n";
	return 0;
}
      day 13
    #include <iostream>
#include <algorithm>
#include <string>
using namespace std;
class Book{
    protected:
        string title;
        string author;
    public:
        Book(string t,string a){
            title=t;
            author=a;
        }
        virtual void display()=0;

};
class MyBook : public Book {
    private:
        int price;
    
    public:
        MyBook(string title, string author, int price) : Book(title, author), price(price) {
            
        }
    
        void display(){
            cout << "Title: " << title << endl;
            cout << "Author: " << author << endl;
            cout << "Price: " << price << endl;
        }
};

int main() {
    string title,author;
    int price;
    getline(cin,title);
    getline(cin,author);
    cin>>price;
    MyBook novel(title,author,price);
    novel.display();
    return 0;
}
	day 14
	#include <iostream>
#include <algorithm>

using namespace std;

class Difference {
    private:
    vector<int> elements;
  
  	public:
  	int maximumDifference;

	Difference(vector<int> arr){
        elements = arr;
        sort(elements.begin(), elements.end());
    }

    void computeDifference(){
        
        maximumDifference = abs(elements[elements.size()-1] - elements[0]);
    }

};

int main() {
    int N;
    cin >> N;
    
    vector<int> a;
    
    for (int i = 0; i < N; i++) {
        int e;
        cin >> e;
        
        a.push_back(e);
    }
    
    Difference d(a);
    
    d.computeDifference();
    
    cout << d.maximumDifference;
    
    return 0;
}
                      day     15
	#include <iostream>
#include <cstddef>
using namespace std;	
class Node
{
    public:
        int data;
        Node *next;
        Node(int d){
            data=d;
            next=NULL;
        }
};
class Solution{
    public:
    Node* insert(Node *head,int data){
      
          if(head == nullptr){
              return new Node(data);
          }
          
          Node *temp = head;
          while(temp->next != nullptr){
              temp = temp->next;
          }
          
          temp->next = new Node(data);          
          return head;
      }
    
      void display(Node *head)
      {
          Node *start=head;
          while(start)
          {
              cout<<start->data<<" ";
              start=start->next;
          }
      }
};
int main()
{
	Node* head=NULL;
  	Solution mylist;
    int T,data;
    cin>>T;
    while(T-->0){
        cin>>data;
        head=mylist.insert(head,data);
    }	
	mylist.display(head);
    return 0;
		
}
	day 16
	#include <bits/stdc++.h>

using namespace std;

int main() {
    string s;
    cin >> s;
    
    try {
        cout << stoi(s) << endl;
    } catch(...) {
        cout << "Bad String" << endl;
    }
    
    return 0;
}




                
               
