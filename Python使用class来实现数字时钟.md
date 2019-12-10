from time import time,localtime,sleep


class Clock:
    def __init__(self, hours, minutes, seconds):
        self.hours = int(hours)
        self.minutes = int(minutes)
        self.seconds = int(seconds)

    def run(self):
        self.seconds += 1
        if self.seconds == 60:
            self.seconds = 0
            self.minutes += 1
            if self.minutes == 60:
                self.minutes = 0
                self.hours += 1
                if self.hours == 24:
                    self.hours = 0

    def show(self):
        print("%02d:%02d:%02d" % (self.hours, self.minutes, self.seconds))


def main(hours, minutes, seconds):
    clock = Clock(hours, minutes, seconds)
    while True:
        clock.show()
        sleep(1)
        clock.run()


if __name__ == "__main__":
    main(23, 59, 58)
