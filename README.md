import google.generativeai as genai

# Configure the API (Replace with your actual API key)
genai.configure(api_key="ENTER_API_KEY")  # 🔹 Ensure you replace this with your real API key

# Define the AI model
model = genai.GenerativeModel("gemini-1.5-pro-latest")  # ✅ Using the correct model

# Function to generate the script
def generate_script(topic):
    """
    Generates a complete script based on the given topic.
    """
    prompt = f"Write a detailed script for '{topic}'. It should have a strong opening, key elements, and a proper ending."
    
    try:
        response = model.generate_content(prompt)
        return response.text  # ✅ Get AI-generated script
    except Exception as e:
        return f"Error: {e}"

# Take user input
topic = input("Start Scripting: ") 

# Generate and print the script
script_output = generate_script(topic)
print("\n🎬 **Generated Script:**\n")
print(script_output)
