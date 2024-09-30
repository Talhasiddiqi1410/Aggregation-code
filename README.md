# Aggregation-code
#include <iostream>
#include <vector>
using namespace std;

class Employee {
public:
    string name;

    Employee(string name) : name(name) {}
};

class Department {
private:
    vector<Employee*> employees;  // Aggregation
public:
    void addEmployee(Employee* employee) {
        employees.push_back(employee);
    }
    void showEmployees() {
        for (auto emp : employees) {
            cout << emp->name << " works in this department." << endl;
        }
    }
};

int main() {
    Employee emp1("John"), emp2("Doe");
    Department dept;
    dept.addEmployee(&emp1);
    dept.addEmployee(&emp2);
    dept.showEmployees();
    return 0;
}

