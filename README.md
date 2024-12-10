```c
#include<iostream>
#define MAX 1000
using namespace std;

int NhapMang(int arr[], int n,int e) {
	cout << "Nhap mang cac so nguyen: ";
	for (int i = 0; i < n; i++) {
		cin >> arr[i];
	}return 0;
}
int XuatMangcacsonguyen(int arr[], int n) {
	for (int i = 0; i < n; i++) {
		cout << arr[i] << " ";
	}return 0;
}
int TinhTong(int arr[], int n) {
	int tong = 0;
	for (int i = 0; i < n; i++) {
		tong += arr[i];
	}return tong;
}
int Tongsole(int arr[], int n) {
	int tong = 0;
	for (int i = 0; i < n; i++) {
		if (arr[i] % 2 != 0)tong += arr[i];
	}return tong;
}
int Demphantu(int arr[], int n) {
	int count = 0;
	for (int i = 0; i < n; i++) {
		if (arr[i] % 2 == 0)count++;
	}return count;
}
bool soGanh(int arr[], int n) {
	for (int i = 0; i < n; i++) {
		if (arr[i] < 100)continue;
		int temp = arr[i], reverse = 0;
		while (temp > 0) {
			reverse = reverse * 10 + (temp % 10);
			temp /= 10;
		}
		if (reverse == arr[i])return true;
	}
	return false;
}
bool ktSoNT(int x) {
		if (x < 2)
			return false;
		for (int i = 2; i <= sqrt(x); i++)
			if (x % i == 0)
				return false;
		return true;
}
void LietKeNT(int arr[], int n) {
	for (int i = 0; i < n; i++) {
		if (ktSoNT(arr[i]))cout << arr[i] << " ";
	}
}
void demChuSo(int a[], int n) {
	for (int i = 0; i < n; ++i) {
		int temp = a[i], count = 0;
		while (temp > 0) {
			++count;
			temp /= 10;
		}
		cout << count << " ";
	}
}
int timsolonnhat(int arr[],int  n) {
	int max = arr[0];
	for (int i = 1; i < n; i++) {
		if (max < arr[i])max = arr[i];
	}
	return max;
}
int timsonhonhat(int arr[], int n) {
	int min = arr[0];
	for (int i = 1; i < n; i++) {
		if (min > arr[i])min = arr[i];
	}
	return min;
}
int timsoChanlonhat(int arr[], int n) {
	int maxChan = arr[0];
	for (int i = 1; i < n; i++) {
		if (maxChan < (arr[i] % 2 == 0))maxChan=arr[i];
	}return maxChan;
}
void tangDan(int arr[], int n) {
	for (int i = 0; i < n - 1; i++) {
		for (int j = i + 1; j < n; j++) {
			if (arr[i] > arr[j]) swap(arr[i], arr[j]);
		}cout << arr[i];
	}
}
void giamDanChuSo(int arr[], int n) {
	for (int i = 0; i < n - 1; i++) {
		for (int j = i + 1; j < n; j++) {
			if (arr[i] % 10 < arr[j] % 10) swap(arr[i], arr[j]);
		
		}cout << arr[i];
	}
}
void tachChanLe(int arr[], int chan[], int le[], int n) {
	int countChan = 0, countLe = 0;
	for (int i = 0; i < n; ++i) {
		if (arr[i] % 2) le[countLe++] = arr[i];
		else chan[countChan++] = arr[i];
	}
}
void themGiaTri(int a[], int n) {
	int value, x;
	cout << "Nhap gia tri: "; cin >> value;
	cout << "Nhap vi tri: "; cin >> x;
	for (int i = n + 1; i > x; --i) a[i] = a[i - 1];
	a[x] = value;
}
void themGiaTriTangDan(int a[], int n) {
	int value;
	cout << "Nhap gia tri: "; cin >> value;
	for (int i = 1; i < n + 1; ++i) {
		if (value >= a[i - 1] && value <= a[i]) {
			for (int j = n + 1; j > i; --j) a[j] = a[j - 1];
			a[i] = value;
			break;
		}
	}
}



int XuatMang(int arr[], int n, int e) {

		switch (e) {
		case 2: cout << "Xuat mang cac so nguyen: "; cout << XuatMangcacsonguyen(arr, n); break;
		case 3: cout << "Tinh tong cac phan tu trong mang: "; cout << TinhTong(arr, n); break;
		case 4: cout << "Tinh tong cac phan tu la so le: "; cout << Tongsole(arr, n); break;
		case 5: cout << "Dem cac phan tu la so chan: "; cout << Demphantu(arr, n); break;
		case 6: cout << "Kiem tra trong mang co ton tai so ganh hay khong?  "; soGanh(arr, n); break;
		case 7: cout << "Liet ke so phan tu la so nguyen to: "; LietKeNT(arr, n); break;
		case 8: cout << "Xuat ra chu so cua moi phan tu: "; demChuSo(arr, n); break;
		case 9: cout << "Tim gia tri lon nhat trong mang: "; cout << timsolonnhat(arr, n); break;
		case 10: cout << "Tim gia tri be nhat trong mang : "; cout << timsonhonhat(arr, n); break;
		case 11: cout << "Tim gia tri chan lon nhat trong mang: "; cout << timsoChanlonhat(arr, n); break;
		case 12: cout << "Sap xep tang dan: "; tangDan(arr, n); break;
		case 13: cout << "Sap xep giam dan theo chu so hang don vi cua moi so : "; giamDanChuSo(arr, n); break;
		case 14: cout << "Tach mang thanh mot mang so chan va mot mang so le : "; break;
		case 15: cout << "Them mot gia tri vao vi tri bat ky trong mang: "; themGiaTri(arr, n); break;
		case 16: cout << "Them mot gia tri vao trong mang da xap xep tang dan ma mang van tang dan: "; themGiaTriTangDan(arr, n); break;
		case 0: cout << "Thoat: "; break;
		}return 0;
	}


int main() {
	int n;
	int e;
	cout << "Nhap vao mot so tuong ung voi cac chuc nang ( nhap 0 de dung!): ";
	cin >> e;
	cout << "Nhap vao mot so nguyen:";
	cin >> n;
	int arr[MAX];
	NhapMang(arr, n,e);
	XuatMang(arr, n,e);
}
```
