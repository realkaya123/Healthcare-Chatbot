from chatterbot import ChatBot
from chatterbot.trainers import ListTrainer
#import os

try:
	os.remove("db.sqlite3")
	print("Old database removed. Training new database")
except:
	print('No database found. Creating new database.')

english_bot = ChatBot('Bot')
trainer=ListTrainer(english_bot)
trainer.train(conv)
trainer.train(conv1)
trainer.train(conv2)
trainer.train(conv3)



from chatterbot import ChatBot
from tkinter import *
i=0
def ptr():
    global i
    f=e.get()
    w=Label(r,text="You: "+e.get(),bg='lightgreen').grid(row=i,column=2)
    i+=1
    t=english_bot.get_response(f)
    ans=str(t)
    w=Label(r,text="Bot: "+ans,bg='white').grid(row=i,column=0)	
    e.delete(0,END)    
    i+=1
r=Tk()
r.title('chatbot')
r.geometry("480x550") 
e=Entry(r)
e.grid(row=20,column=1)
b=Button(r,text="Send",width=10,command=ptr)
b.grid(row=20,column=2)
i=i+1
mainloop()








conv=["hi","hello,Welcome to MediCare","how are you","i m fine, what about you","i am not feeling well","please tell your symptoms"]
conv1=["My body temperature has raised.","This is a symptom of fever, you should take a tablet of crocin after you have your meal.","Ok, i will take the crocin.","ok,take care","thankuu","welcome","I am shivering","This is a symptom of fever, you should take a tablet of crocin after you have your meal.",
       "ok,fine","get well soon","thankyou","your welcome","I am feeling weak.","This is a symptom of fever, you should take a tablet of crocin after you have your meal.","ok,thank you","take care, get well soon"]
conv2=["my hand is aching.","okay, did you get hurt, or it is a suddern aching.","my joint is aching.",
       "okay, did you get hurt, or it is a suddern aching.","yes i got hurt.",
       "ok, is there a swelling or a physical deformity or bleeding at the aching region.","yes there is a swelling",
       "it is a common symptom of fracture, should I book an an appointment for you.","yes there is a physical deformity.",
"it is a common symptom of fracture,you should go and see a doctor immediately."]
conv3=["my nose is choked","Okay, this is a symptom of cold,You should take a sudafed tablet after your meal.",
      "I am still not feeling well","okay,then you should consult your doctor","I have a cough","You should take a spoon full of benadryl after your meal","ok","take rest"," my throat is itching","Okay, this is a symptom of cough,You should take a spoon full of benadryl after your meal"]
