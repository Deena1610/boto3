pip install flask
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route("/")
def home():
    return "வணக்கம்! இது உங்கள் AI-powered website."

@app.route("/predict", methods=["POST"])
def predict():
    data = request.json
    user_input = data.get("input", "")
    response = f"நீங்கள் சொன்னது: {user_input}. நான் உங்களுக்கு உதவுகிறேன்!"
    return jsonify({"response": response})

if __name__ == "__main__":
    app.run(debug=True)
		
