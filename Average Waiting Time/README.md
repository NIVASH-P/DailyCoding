Average Waiting Time

Program:

double averageWaitingTime(vector<vector<int>>& customers) {
        int st = customers[0][0], tot = 0;
        vector<int> wait;
        for (auto& i : customers) {
            if (st <= i[0]) {
                st = i[0];
            }
            int fin = st + i[1];
            int w = fin - i[0];
            cout << w << endl;
            wait.push_back(w);
            st = fin;
        }
        double ans = 0, n = wait.size();
        for (auto& i : wait) {
            ans += i;
        }
        ans = (ans / n);
        return ans;
    }
