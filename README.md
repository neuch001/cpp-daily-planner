#include <iostream>
#include <vector>
#include <string>
#include <cstdlib>
using namespace std;

int main() {
    setlocale(LC_ALL, "ru");

    vector<string> tasks;
    int choice;
    string task;

    while (true) {
        system("cls");
        cout << "==============================\n";
        cout << "        ЕЖЕДНЕВНИК v1.0       \n";
        cout << "==============================\n";
        cout << "1. Добавить задачу\n";
        cout << "2. Показать все задачи\n";
        cout << "3. Удалить задачу\n";
        cout << "4. Выйти\n";
        cout << "------------------------------\n";
        cout << "Ваш выбор: ";
        cin >> choice;
        cin.ignore();

        if (choice == 1) {
            system("cls");
            cout << "Введите задачу: ";
            getline(cin, task);
            tasks.push_back(task);
            cout << "\nЗадача добавлена!\n";
            system("pause");
        }
        else if (choice == 2) {
            system("cls");
            if (tasks.empty()) {
                cout << "Список задач пуст.\n";
            } else {
                cout << "Ваши задачи:\n";
                for (int i = 0; i < tasks.size(); i++) {
                    cout << i + 1 << ". " << tasks[i] << endl;
                }
            }
            cout << endl;
            system("pause");
        }
        else if (choice == 3) {
            system("cls");
            if (tasks.empty()) {
                cout << "Список задач пуст, нечего удалять.\n";
            } else {
                cout << "Введите номер задачи для удаления:\n";
                for (int i = 0; i < tasks.size(); i++) {
                    cout << i + 1 << ". " << tasks[i] << endl;
                }
                cout << "\nНомер: ";
                int index;
                cin >> index;

                if (index > 0 && index <= tasks.size()) {
                    tasks.erase(tasks.begin() + index - 1);
                    cout << "\nЗадача удалена!\n";
                } else {
                    cout << "\nНекорректный номер.\n";
                }
            }
            system("pause");
        }
        else if (choice == 4) {
            system("cls");
            cout << "Выход из программы...\n";
            break;
        }
        else {
            cout << "Неверный пункт меню, попробуйте снова.\n";
            system("pause");
        }
    }

    return 0;
}
