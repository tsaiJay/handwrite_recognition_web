# Handwrite Digit Recognition Webapp

!!!!!!!!!!!!!! AI model not complete  !!!!!!!!!!!!!!

This project integrates a Flask-based web service with PyTorch to provide handwritten digit recognition, allowing users to draw digits directly on a web page for real-time analysis.

## Requirements

- Python >= 3.8
- Flask
- Flask-Cors
- PyTorch
- torchvision
- Pillow

## Setup Instructions

1. **Clone the repository:**

   ```bash
   git clone https://github.com/tsaiJay/handwrite_recognition_web.git
   cd handwrite_recognition_web
   ```

2. **Set up a virtual environment:**

   You can use `venv` to create a virtual environment. Run the following command:

   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment:**

   - On Windows:

     ```bash
     venv\Scripts\activate
     ```

   - On macOS/Linux:

     ```bash
     source venv/bin/activate
     ```

4. **Install the required packages:**

   With the virtual environment activated, run:

   ```bash
   pip install -r requirements.txt
   ```

5. **Train and Evaluate the Model (optional):**

   If you want to train the model yourself, you can use the `train.py` script, which utilizes the MNIST dataset to train a simple CNN model. Run the following command to train the model:

   ```bash
   cd ai_model/train_from_scratch
   python train.py
   ```

   The trained model will be saved as 'lenet.pt' in the same directory. After training, you can evaluate the model's performance using the `eval.py` script. To do this, run the following command:

   ```bash
   python eval.py
   ```

   This will output the test accuracy of the model on one of the MNIST dataset.

6. **Run the server:**

   Start the Flask server by executing:

   ```bash
   python server.py
   ```

   The server will run on `http://127.0.0.1:5000`.

## API Endpoints

- **POST /classify**

  This endpoint accepts a base64-encoded image of a handwritten digit and returns the predicted digit and confidence level.

  **Request Example:**

  ```json
  {
      "image": "data:image/png;base64,<base64-image-data>"
  }
  ```

  **Response Example:**

  ```json
  {
      "digit": 7,
      "confidence": 0.98
  }
  ```

## Usage

You can use tools like Postman or cURL to test the `/classify` endpoint by sending a POST request with the base64-encoded image data.

## License

This project is licensed under the MIT License. 
