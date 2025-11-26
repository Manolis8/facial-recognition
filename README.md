Facial Recognition System

A Python-based facial recognition system using face_recognition and OpenCV. The system allows you to:  

1. Capture headshots for each person.  
2. Train a model to recognize faces.  
3. Run a live facial recognition session using your webcam.  

---

Folder Structure

facial-recognition/
├── dataset/                # Folder to store headshots of each person
│   ├── Name1/
│   ├── Name2/
│   └── ...
├── headshots.py            # Script to capture photos of individuals
├── train_model.py          # Script to train the facial recognition model
├── facial_recognition.py   # Script to run live recognition
├── encodings.pickle        # Generated model file (after training)
├── requirements.txt        # Dependencies
└── README.txt

Important: Create a folder called dataset before starting. Inside it, create a folder for each person you want to recognize (e.g., dataset/Mike).

---

Setup

1. Clone the repository:
git clone https://github.com/Manolis8/facial-recognition.git
cd facial-recognition

2. Install dependencies:
pip install -r requirements.txt

---

Step 1: Capture Headshots

Run headshots.py to take pictures of each person:  
python headshots.py

- Replace the variable name with the person’s name.  
- Press SPACE to capture a photo.  
- Press ESC to exit.  
- Tip: Take 100+ photos per person from multiple angles, lighting conditions, and expressions.  

All images are saved in dataset/<Name>/.

---

Step 2: Train the Model

Once you have enough images, run train_model.py to generate facial encodings:  
python train_model.py

This will:  
- Read all images in the dataset folder.  
- Detect faces and generate embeddings.  
- Save the encodings to encodings.pickle.  

---

Step 3: Run Live Facial Recognition

Run facial_recognition.py to start detecting faces in real-time:
python facial_recognition.py

- The system uses the webcam and identifies people from encodings.pickle.  
- Recognized faces will display their names on screen.  
- Press Q to quit.  

---

Tips for Better Accuracy

- Take many photos from different angles, expressions, and lighting conditions.  
- Avoid blurry images.  
- Keep the background simple for training.  
- Make sure each person has their own folder in dataset/.  
- Re-train the model after adding more images.  

---

How it Works

1. headshots.py – Captures images of individuals.  
2. train_model.py – Processes images, extracts face encodings, and serializes them to encodings.pickle.  
3. facial_recognition.py – Uses webcam feed to detect and recognize faces in real-time using the trained encodings.  

---

Notes

- Make sure dataset/ exists and has at least a few images per person before training.  
- The larger and more varied your dataset, the better the recognition accuracy.  
- Designed for educational and demo purposes.
