import sys

from PyQt5.QtWidgets import QMainWindow, QApplication
from PyQt5 import uic


class App(QMainWindow):
    def __init__(self):
        super().__init__()
        uic.loadUi('calc_grafic.ui', self)
        self.one.clicked.connect(self.one_k)
        self.two.clicked.connect(self.two_k)
        self.three.clicked.connect(self.three_k)
        self.four.clicked.connect(self.four_k)
        self.five.clicked.connect(self.five_k)
        self.six.clicked.connect(self.six_k)
        self.seven.clicked.connect(self.seven_k)
        self.eight.clicked.connect(self.eight_k)
        self.nine.clicked.connect(self.nine_k)
        self.zero.clicked.connect(self.zero_k)
        self.plus.clicked.connect(self.plus_k)
        self.minus.clicked.connect(self.minus_k)
        self.equal.clicked.connect(self.equal_k)
        self.divide.clicked.connect(self.divide_k)
        self.multiply.clicked.connect(self.multiply_k)
        self.c_bt.clicked.connect(self.c_k)
        self.ac_bt.clicked.connect(self.ac_k)

    nums = []

    def one_k(self):
        App.nums.append('1')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def two_k(self):
        App.nums.append('2')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def three_k(self):
        App.nums.append('3')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def four_k(self):
        App.nums.append('4')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def five_k(self):
        App.nums.append('5')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def six_k(self):
        App.nums.append('6')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def seven_k(self):
        App.nums.append('7')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def eight_k(self):
        App.nums.append('8')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def nine_k(self):
        App.nums.append('9')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def zero_k(self):
        App.nums.append('0')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def plus_k(self):
        App.nums.append('+')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def minus_k(self):
        App.nums.append('-')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def multiply_k(self):
        App.nums.append('*')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def divide_k(self):
        App.nums.append('/')
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)

    def equal_k(self):
        txt = str(eval(''.join(App.nums)))
        if len(self.label.text()) != 0:
            self.label.setText(txt)

    def c_k(self):
        try:
            App.nums.pop(-1)
            txt = ''.join(App.nums)
            if len(self.label.text()) != -1:
                self.label.setText(txt)
        except:
            App.nums.append(1)
            App.nums.pop(-1)
            txt = ''.join(App.nums)
            if len(self.label.text()) != -1:
                self.label.setText(txt)

    def ac_k(self):
        App.nums.clear()
        txt = ''.join(App.nums)
        if len(self.label.text()) != -1:
            self.label.setText(txt)


if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = App()
    window.show()
    sys.exit(app.exec())
