
/*#include <iostream> //2
using namespace std;
int main() {
    for (int i = 1; i <= 9; ++i) {
        for (int j = 1; j <= 9; ++j) {
            cout << j << "x" << i << "=" << (j * i) << " ";
        }
    }
    return 0;
}



#include <iostream> //3
using namespace std;
int main() {
    int a, b;
    cout << "두 수를 입력하라:";
    cin >> a >> b;

    int max = (a > b) ? a : b;
    cout << "큰 수 = " << max << endl;

    return 0;
}


#include <iostream> //4
using namespace std;

int main() {

    double numbers[5];
    double max;

    cout << "5 개의 실수를 입력하라: ";
    for (int i = 0; i < 5; i++) {
        cin >> numbers[i];
    }
    max = numbers[0];

    for (int i = 1; i < 5; i++) {
        if (numbers[i] > max) {
            max = numbers[i];
        }
    }

    cout << "제일 큰 수 = " << max << endl;

    return 0;
}

#include <iostream> //5
using namespace std;

int main() {
    char in[100];
    int count = 0;

    cout << "문자들을 입력하라(100개 미만). \n";
    cin.getline(in, 100);

    for (int i = 0; in[i] != '\0'; ++i) {
        if (in[i] == 'x') {
            count++;
        }
    }

    cout << "x의 개수는 " << count << endl;

    return 0;
}

#include <iostream> //6
#include <string>
using namespace std;

int main() {
   string p1, p2;

    cout << "새 암호를 입력하세요:";
    cin >> p1;
    cout << "새 암호를 다시 한 번 입력하세요:";
    cin >> p2;

    if (p1 == p2) {
        cout << "같습니다." <<endl;
    }
    else {
        cout << "같지 않습니다." << endl;
    }

    return 0;
}

#include <iostream> //7
#include <cstring>
using namespace std;

int main() {
    char input[100];

    while (true) {
        cout << "종료하고싶으면 yes를 입력하세요:";
        cin.getline(input, 100);

        if (strcmp(input, "yes") == 0) {
            cout << "종료합니다..." << endl;
            break;
        }
    }

    return 0;
}*/

#include <iostream> //8
#include <cstring>
using namespace std;

int main() {
    char name[100]; 
    cout << "5 명의 이름을 ';'으로 구분하여 입력하세요: \n";
    cin.getline(name, 100);

  
    char names[5][100]; 
    int count = 0; 
    int max = 0; 
    string longname; 

  
    int s = 0; 
    for (int i = 0; i < strlen(name); i++) {
        if (name[i] == ';' || name[i] == '\0') {
           
            if (count < 5) {
               
                strncpy_s(names[count], &name[s], i - s);
                names[count][i - s] = '\0'; 
                cout << count + 1 << " : " << names[count] << endl;

              
                int length = strlen(names[count]);
                if (length > max) {
                    max = length;
                    longname = names[count]; 
                }

                count++;
            }
            s = i + 1; 
        }
    }

  
    cout << "가장 긴 이름은 " << longname << endl;

    return 0;
}
