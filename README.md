# IFC AI Assistant - Technical Approach

## Introduction
This project creates a conversational AI that analyzes IFC (Industry Foundation Classes) files to answer questions about building elements. It combines NLP for understanding queries with IfcOpenShell for processing BIM data.

## How I Built It

### Core Components
1. **Natural Language Processing (NLP)**
   - Uses NLTK for tokenization and lemmatization
   - Rule-based intent detection with POS tagging
   - Handles queries like:
     - "How many walls?"
     - "What's the total slab volume?"
     - "Show plastering areas"

2. **IFC Processing Engine**
   - IfcOpenShell for geometry extraction
   - Calculates:
     - Surface areas (for plastering)
     - Volumes (for materials)
     - Element counts
   - Handles property extraction

3. **Conversational Interface**
   - Flask web backend
   - Simple JavaScript frontend
   - Error-tolerant design

### Key Technical Choices
- **Rule-based NLP**: More reliable than ML for domain-specific queries
- **Geometry Fallbacks**: Uses both geometric calculations and property sets
- **Modular Design**: Separates NLP, IFC processing, and UI layers

## Architecture
[User Input] → [NLP Processing] → [IFC Analysis] → [Response Generation]

### 2. **Setup Instructions (README.md)**

```markdown
# IFC AI Assistant

A conversational interface for querying IFC building models.

## Installation

1. **Prerequisites**
   - Python 3.10 - 3.11
   - IFC file to analyze (i can provide the file )

2. **Setup** 

   git clone [https://github.com/Mukeshkummuru/ifc_AI_agent]
   create a virtual env(if needed)
   Then open termianl [ pip install ifcopenshell flask numpy nltk ] - these are the required packages must
   open apprun.py(if it is in visual studio click the top right play button to run)
   or
   in terminal type (python apprun.py)


Running the Application :-
Then open the provided link in the terminal given in your browser

Testing with Sample Queries
Try these examples:

"How many walls in the model?"

"Calculate total plastering area"

"What's the slab volume?"


# Example Interactions(sample outputs)

## Query 1: Counting Elements
You: how much plastering is done
Bot: Total plastering area is 2908.24 square meters.

## Query 2: Material Calculations  
You: how many walls are there
Bot: There are 191 walls in the model.

## Query 3: Volume Measurement  
You: total volume of the walls
Bot: Total volume of all walls is 89.26 cubic meters.

## Query 4: Error Handling  
You: total volume of the slab
Bot: The total slab volume is approximately 98.42 cubic meters.

## Query 5: Detailed Request  
You: area of the walls
Bot: The total wall surface area is approximately 2908.24 square meters.

## Query 5: Detailed Request (For error handling)
You: how are you ai
Bot: I'm sorry, I didn't understand that. Could you please rephrase?