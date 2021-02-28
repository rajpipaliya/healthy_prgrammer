# healthy_prgrammer

from pygame import mixer
from time import time
from datetime import datetime

def musiconloop(file , stopper):
    mixer.init()
    mixer.music.load(file)
    mixer.music.play()
    while True:
        a=input()
        if a==stopper:
            mixer.music.stop()
            break
    
def log_now(msg):
        with open("mylogs.txt",'a') as f:
            f.write(f"{msg} {datetime.now()}\n")

if __name__== '__main__':
    #musiconloop("example.mp3","stop")
    init_water=time()
    init_eyes=time()
    init_exercise=time()
    watersecs= 40*60
    exsecs = 30*60
    eyessecs = 45*60

    while True:
        if time()-init_water > watersecs:
            print("water drinking time enter drank to stop:")
            musiconloop("water.mp3", "drank")
            init_water=time()
            log_now("drank water at ")


        if time()-init_eyes > eyessecs:
            print("eyes time enter eyesdone to stop:")
            musiconloop("eyes.mp3", "eyesdone")
            init_eyes=time()
            log_now("eyes done at ")

        if time()-init_exercise > exsecs:
            print("exercise time enter exdone to stop:")
            musiconloop("ex.mp3", "exdone")
            init_exercise=time()
            log_now("exercise done  at ")

        
