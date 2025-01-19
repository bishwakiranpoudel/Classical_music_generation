# Classical Music Generation using LSTM

This project demonstrates how to generate classical music using a Long Short-Term Memory (LSTM)-based neural network. The model is trained on MIDI files to predict sequences of notes, offsets, and durations, enabling the creation of new musical compositions.

## Features

- **Data Extraction**: Extracts musical components such as notes, offsets, and durations from MIDI files.
- **Custom Dataset**: Implements a PyTorch `Dataset` for seamless data handling.
- **Multi-Task Learning**: Simultaneously predicts notes, offsets, and durations using a combined LSTM architecture.
- **Music Generation**: Produces MIDI files based on the trained model's predictions.

---

## Requirements

### Dependencies

To set up the project, ensure the following libraries are installed:

- Python 3.x
- Required libraries:
  ```bash
  pip install torch torchvision numpy music21 tensorflow
  ```

### File Structure

- Place your MIDI files in the directory: `./midi_songs/`
- Ensure this script (`Classical Music Generation.ipynb`) is located in the root directory.

---

## Code Overview

### 1. **Data Preprocessing**

- **`get_notes()`**: Parses MIDI files to extract notes, offsets, and durations.
- **`prepare_sequences()`**: Converts these components into input-output sequences suitable for training.

### 2. **Model Architecture**

- **Three LSTM Streams**: Separate LSTM layers for notes, offsets, and durations.
- **Combined LSTM**: Merges the outputs from the three streams into a shared layer.
- **Fully Connected Layers**: Predicts the next notes, offsets, and durations.

### 3. **Training**

- **Custom Dataset**: A PyTorch dataset class is implemented to handle input-output pairs.
- **Training Loop**: Utilizes cross-entropy loss and Adam optimizer to train the model efficiently.

### 4. **Music Generation**

- **`generate_notes()`**: Uses the trained model to create sequences of notes, offsets, and durations.
- **`create_midi()`**: Converts the generated sequences into a playable MIDI file.

---

## How to Use

1. **Prepare the Dataset**

   - Place your MIDI files in the `./midi_songs/` directory.

2. **Run the Jupyter Notebook**

   - Open `Classical Music Generation.ipynb` in Jupyter Notebook or Google Colab.

3. **Train the Model**

   - Execute the cells to preprocess data, train the model, and save it as `trained_model.pth`.

4. **Generate Music**
   - Use the `generate()` function to create a new MIDI file.
   - The output file will be saved as `test_output.mid`.

---

## Output

- **`test_output.mid`**: The generated MIDI file, ready to be played using any MIDI player.

---

## Notes

- Parameters like sequence length, batch size, and learning rate can be adjusted within the notebook.
- Ensure the dependencies are properly installed to avoid compatibility issues.
