import os
import json

filename= "planner.json"
if os.path.exists(filename):
  with open(filename,"r")as f:
    videos=json.load(f)
else:
  videos={}

def plan_video():
  vid_id= input("video id:").strip().upper()
  title= input("Video title: ").strip()
  tags_input = input("enter tags separate by comma: ").strip()
  tags_list= [t.strip() for t in tags_input.split(".")]
  videos[vid_id]={"title":title,"tags":tags_list,"status":"planning"}
  print(f"✅ {vid_id} added to the planner!")


def show_planner():
  print("\n--- 🎬 CONTENT PLAN ---")
  for id, info in videos.items():
    print(f"ID: {id} | Title: {info['title']}")
    print(f"🏷️ Tags: {', '.join(info['tags'])}")
    print("-" * 30)

while True:
    print("\n1. View Planner\n2. Plan New video \n3. Save & Exit")
    cmd = input("Choice: ")

    if cmd == "1":
        show_planner()
    elif cmd == "2":
        plan_video()
    elif cmd == "3":
        with open(filename, "w") as f:
            json.dump(videos, f, indent=4)
        break
    else:
        print("invalid choice..")
