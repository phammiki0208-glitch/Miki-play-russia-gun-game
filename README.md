
#include <iostream>
#include <ctime>
#include <cstdlib>
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

void playGame() {
    // Khởi tạo bộ tạo số ngẫu nhiên dựa trên thời gian thực
    srand(time(0));

    int bulletPosition = rand() % 6; // Vị trí đạn từ 0 đến 5
    int currentChamber = 0;
    bool gameOver = false;
    string players[] = {"Người chơi", "Máy"};
    int turn = 0; // 0 là người, 1 là máy

    cout << "--- CHAO MUNG DEN VOI TRO CHOI VONG QUAY MAY MAN ---" << endl;
    cout << "Co 1 vien dan trong o xo 6 cho. Bat dau thoi!" << endl << endl;

    while (!gameOver) {
        cout << "Luot cua: " << players[turn] << endl;
        
        if (turn == 0) {
            cout << "Nhan Enter de bop co...";
            cin.get(); // Đợi người dùng nhấn Enter
        }

        cout << "* Tach! *" << endl;

        if (currentChamber == bulletPosition) {
            cout << "BANG!!! " << players[turn] << " da hy sinh!" << endl;
            cout << "Tro choi ket thuc." << endl;
            gameOver = true;
        } else {
            cout << "May man thay, buong dan nay trong." << endl << endl;
            currentChamber++;
            turn = 1 - turn; // Đổi lượt (0 -> 1, 1 -> 0)
        }
    }
}

int main() {
    playGame();
    return 0;
}
