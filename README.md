# Final
#include <cstdlib>
#include <iostream>
#include <limits> // Needed for numeric_limits<streamsize>::max()
#include <fstream>
#include <iostream>

using namespace std;

void displayMainMenu();
void displayFootballTeam();
void displayFootballPlayers();
void displayFootballSchedule();
void displayFootballRules();
void displayVolleyballTeam();
void displayVolleyballPlayers();
void displayVolleyballSchedule();
void displayVolleyballRules();
int loadMyList();
bool saveMyList();

const int MYLISTSIZE = 10;
string myList[MYLISTSIZE];

int main() {
    displayMainMenu();

    return 0;
}

void displayMainMenu() {
    int choice = -1;
    while (choice != 0) {
        cout << "===============================\n";
        cout << "       Intramural Sports\n";
        cout << "===============================\n";
        cout << "1. Football\n";
        cout << "2. Volleyball\n";
        cout << "0. Exit\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 11) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "===========================\n";
            cout << "          Football\n";
            cout << "===========================\n";
            cout << "3.  Teams\n";
            cout << "4.  Players\n";
            cout << "5.  Schedule\n";
            cout << "6.  Rules\n";
            cout << "11. Main Menu\n";
            cout << "0.  Exit\n";
            cout << "\n";
            cout << "Please enter a menu selection: ";
            cin >> choice;
            break;
        case 2:
            cout << "===========================\n";
            cout << "          Volleyball\n";
            cout << "===========================\n";
            cout << "7.  Teams\n";
            cout << "8.  Players\n";
            cout << "9.  Schedule\n";
            cout << "10. Rules\n";
            cout << "11. Main Menu\n";
            cout << "0.  Exit\n";
            cout << "\n";
            cout << "Please enter a menu selection: ";
            cin >> choice;
            break;
        case 3:
            displayFootballTeam();
            system("cls");
            break;
            
        case 4:
            displayFootballRules();
            system("cls");
            break;
            
        case 5:
            displayFootballSchedule();
            system("cls");
            break;
            
        case 6:
            displayFootballRules();
            system("cls");
            break;  
            
        case 7:
            displayVolleyballTeam();
            system("cls");
            break;
            
        case 8:
            displayVolleyballPlayers();
            system("cls");
            break;
            
        case 9:
            displayVolleyballSchedule();
            system("cls");
            break;
            
        case 10:
            displayVolleyballRules();
            system("cls");
            break;
            
        case 11:
            cout << "===============================\n";
            cout << "       Intramural Sports\n";
            cout << "===============================\n";
            cout << "1. Football\n";
            cout << "2. Volleyball\n";
            cout << "0. Exit\n";
            cout << "\n";
            cout << "Please enter a menu selection: ";
            cin >> choice;
        }
    }
}

void displayFootballTeam() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

void displayFootballPlayers() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

void displayFootballSchedule() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

void displayFootballRules() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

void displayVolleyballTeam() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

void displayVolleyballPlayers() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

void displayVolleyballSchedule() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

void displayVolleyballRules() {
    system("cls");
    int updateChoice = -1;
    int deleteChoice = -1;

    int choice = -1;

    while (choice != 0) {
        cout << "===============================\n";
        cout << "          Football Team\n";
        cout << "===============================\n";

        int recordCount = loadMyList();

        cout << "\n";
        cout << "1. Add\n";
        cout << "2. Update\n";
        cout << "3. Delete\n";
        cout << "0. Return to the Main Menu\n";

        cout << "\n";
        cout << "Please enter a menu selection: ";
        cin >> choice;

        while (cin.fail() || choice < 0 || choice > 3) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(),'\n');
            cout << "\n";
            cout << "Please enter a VALID menu selection: ";
            cin >> choice;
        } // end of inner while loop

        switch(choice) {
        case 0:
            return;
        case 1:
            cout << "\n";
            if (recordCount >= MYLISTSIZE) {
                cout << "Sorry List is Full\n\n";
            } else {
                cout << "Enter a new list item: ";
                cin >> myList[recordCount];

                bool saveSuccess = saveMyList();
                if(saveSuccess) system("cls");

            }
            break;

        case 2:
            updateChoice = -1;
            cout << "Enter a list item number to be updated or 0 to return: ";
            cin >> updateChoice;

            while (cin.fail() || updateChoice < 0 || updateChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be updated or 0 to return: ";
                cin >> updateChoice;
            } // end of inner while

            if (updateChoice == 0) {
                system("cls");
            } else {
                cout << "Updated item: ";
                cin >> myList[updateChoice-1];

                if(saveMyList()) system("cls");  // only clear the screen
            }

            break;

        case 3:
            deleteChoice = -1;
            cout << "Enter a list item number to be deleted or 0 to return: ";
            cin >> deleteChoice;

            while (cin.fail() || deleteChoice < 0 || deleteChoice > recordCount) {
                cin.clear();
                cin.ignore(numeric_limits<streamsize>::max(),'\n');
                cout << "\n";
                cout << "Please enter a VALID item to be deleted or 0 to return: ";
                cin >> deleteChoice;
            } // end of inner while

            if (deleteChoice == 0) {
                system("cls");
            } else {
                myList[deleteChoice-1] = "";
                if(saveMyList()) system("cls");  // only clear screen if successful
            }

            break;
        } // end of switch statement

    } // end of while loop for redisplaying the sub menu
}

int loadMyList() {
    int recordCount = 0;

    ifstream inFile("myList.txt");

    if(inFile.fail()) {
        cout << "ERROR:: Unable to open myList.txt!!!\n\n" << endl;
        return 0; // no records loaded
    }

    cout << "\n";
    cout << "My List:\n";
    while(inFile >> myList[recordCount]) {
        cout << "    " << recordCount+1 << ". " << myList[recordCount] << "\n";
        recordCount++;
    }
    if(recordCount==0) cout << "My List is EMPTY :(\n\n";

    inFile.close();

    for(int j=recordCount; j < MYLISTSIZE; j++) {
        myList[j] = "";  //set the remanding array elements to an empty string
    }

    return recordCount;
}

bool saveMyList() {
    ofstream outFile("myList.txt");

    if(outFile.fail()) {
        cout << "\n";
        cout << "ERROR:: Unable to save MyList.txt!\n\n";
        return false;
    }

    for (int i=0; i < MYLISTSIZE; i++) {
        if(myList[i]> "") {
            outFile << myList[i] << "\n";
        }
    }

    outFile.close();
    return true;
}
