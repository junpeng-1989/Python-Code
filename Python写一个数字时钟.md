class Clock:
    def __init__(self, hour, minutes,seconds):
        self.hour = int(hour)
        self.minutes = int(minutes)
        self.seconds = int(seconds)

    def run(self):
        self.seconds += 1
        if self.seconds == 60:
            self.minutes += 1
            self.seconds = 0
            if self.minutes == 60:
                self.hour += 1
                self.minutes = 0
                if self.hour == 24:
                    self.hour = 0

    def show(self):
        print("%02d:%02d:%02d" % (self.hour,self.minutes,self.seconds))


clock = Clock('23', '59', '59')
while True:
    # clock.show()
    time.sleep(1)
    clock.run()
    clock.show()
