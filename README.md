# Scripting-AI-3.0
import google.generativeai as genai

# Configure the API (Replace with your actual API key)
genai.configure(api_key="AIzaSyC2xdAWFYn-a725P2zm3b_evzYFwQ6Sj1U")  # 🔹 Ensure you replace this with your real API key

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

# Loop to generate multiple scripts
while True:
    topic = input("\n🎬 Enter a topic for scripting (or type 'exit' to stop): ") 
    if topic.lower() == "exit":
        print("\n🚪 Exiting script generation. Goodbye!")
        break  # Stop the loop
    
    # Generate and print the script
    script_output = generate_script(topic)
    print("\n🎬 **Generated Script:**\n")
    print(script_output)
    print("\n" + "="*50)  # Separator for readability
