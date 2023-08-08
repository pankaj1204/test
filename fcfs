#include<iostream>
using namespace std;

const int maxProcesses = 100; // Assuming a maximum of 100 processes

void findavgTime(int n, int bt[]) {
    int wt[maxProcesses] = {0}, tat[maxProcesses] = {0};
    int total_wt = 0, total_tat = 0;

    for (int i = 1; i < n; i++) {
        wt[i] = bt[i - 1] + wt[i - 1];
        tat[i] = bt[i] + wt[i];
        total_wt += wt[i];
        total_tat += tat[i];
    }

    cout << "Processes\tBurst time\tWaiting time\tTurnaround time\n";

    for (int i = 0; i < n; i++) {
        cout << i + 1 << "\t\t" << bt[i] << "\t\t" << wt[i] << "\t\t" << tat[i] << endl;
    }

    cout << "Average waiting time = " << (float)total_wt / n << endl;
    cout << "Average turnaround time = " << (float)total_tat / n << endl;
}

int main() {
    int n;
    int burst_time[maxProcesses];

    cout << "Enter the number of processes: ";
    cin >> n;

    if (n <= 0 || n > maxProcesses) {
        cout << "Invalid number of processes. Please enter a value between 1 and " << maxProcesses << "." << endl;
        return 1; // Exit with an error code
    }

    for (int i = 0; i < n; i++) {
        cout << "Enter burst time for process " << i + 1 << ": ";
        cin >> burst_time[i];
    }

    findavgTime(n, burst_time);
    return 0;
}
