# Maximum-yield-6
Maximum yield

#include <iostream>
#include <vector>
#include <assert.h>

using namespace std;

int Maximum_Yield(const vector<int>& units) {
  if (units.size() == 0) {
    return 0;
  }
  int a = 0, b = units[0];
  for (int i = 1; i < units.size(); ++i) {
    int tmp = b;
    b = max(units[i] + a, b);
    a = tmp;
  }
  return b;
}

void main() {
  vector<int> test1;
  test1.push_back(206);
  test1.push_back(140);
  test1.push_back(300);
  test1.push_back(52);
  test1.push_back(107);
  assert(613 == Maximum_Yield(test1));

  vector<int> test2;
  test2.push_back(147);
  test2.push_back(206);
  test2.push_back(52);
  test2.push_back(240);
  test2.push_back(300);
  assert(506 == Maximum_Yield(test2));

  system("pause");
}
