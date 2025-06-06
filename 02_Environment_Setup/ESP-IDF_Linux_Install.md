
# **ESP-IDF Installation on Linux**

## **Step 1: Install Prerequisites**

```bash
sudo apt-get install git wget flex bison gperf python3 python3-pip python3-venv cmake ninja-build ccache libffi-dev libssl-dev dfu-util libusb-1.0-0
```

## **Step 2: Get ESP-IDF**

### **Clone the ESP-IDF Repository:**

1. **Create a `development` directory:**
   ```bash
   mkdir development
   cd development
   ```

2. **Clone the ESP-IDF repository from GitHub:**
```bash
mkdir -p ~/esp
cd ~/esp
git clone -b v5.4.1 --recursive https://github.com/espressif/esp-idf.git
```

### **Install ESP-IDF Tools:**

1. **Go to the ESP-IDF directory:**
   ```bash
   cd esp-idf
   ```

2. **Run the installation script to install necessary tools for the ESP32:**
   ```bash
   ./install.sh esp32
   ```

   For multiple boards (e.g., ESP32, ESP32-S2), you can run:
   ```bash
   ./install.sh esp32,esp32s2
   ```

   To install tools for all supported boards:
   ```bash
   ./install.sh all
   ```

   Alternatively, if you're using the fish shell:
   ```bash
   ./install.fish esp32
   ```

   For multiple boards with fish shell:
   ```bash
   ./install.fish esp32,esp32s2
   ```

   Or, to install tools for all supported boards:
   ```bash
   ./install.fish all
   ```

---

## **Step 3: Set Up the Environment Variables**

ESP-IDF needs to have certain environment variables set in order to work correctly.

### **Export Environment Variables:**

1. **Run the `export.sh` script:**
   This will set up the necessary environment variables for your shell session.

   ```bash
   . ./export.sh
   ```

   **Note:** You need to run this every time you open a new terminal session to use ESP-IDF tools. You can add this line to your shell’s startup script (e.g., `.bashrc` or `.zshrc`) to make it permanent.

---

## **Step 4: Verify the Installation**

### **Check Python and ESP-IDF Setup:**

1. **Check Python version:**
   Run the following to make sure Python is correctly set up:
   ```bash
   python3 --version
   ```

2. **Check if ESP-IDF is set up correctly:**
   Run this to verify if everything is set up:
   ```bash
   idf.py --version
   ```

---

## **Step 5: Additional Configurations**

### **Set up `ESP_IDF` Environment Variable (Optional):**

To simplify the process, you can set an environment variable to the path of your ESP-IDF directory.

1. Open your `.bashrc` or `.zshrc` file:
   ```bash
   nano ~/.zshrc  # or ~/.bashrc if you use zsh
   ```

2. Add the following line at the end of the file:
   ```bash
   # Set ESP-IDF path
    alias get_idf="source /home/karthikeyana/development/esp/esp-idf/export.sh"
   ```

   Replace `/home/your_user_name/developmentesp/esp-idf` with the correct path to your ESP-IDF directory.

3. **Apply changes:**
   ```bash
   source ~/.zshrc  # or source ~/.bashrc
   ```

---

## **Step 6: Create and Build Projects**

### **Create a New Project:**

To create a new project, use the `idf.py` tool:
```bash
idf.py create-project my_project
```

### **Build the Project:**

Navigate to your project directory and build the project:
```bash
cd my_project
idf.py set-target esp32
idf.py menuconfig
```
![img0](https://github.com/user-attachments/assets/ddf90703-9ae7-4fd2-a396-4790211b48d0)
![img1](https://github.com/user-attachments/assets/7b417545-8922-4a56-9dda-c10ab12cbe9c) 
![img2](https://github.com/user-attachments/assets/a9ce9a02-c911-4738-8ad4-a2cbde9cc555)
![img3](https://github.com/user-attachments/assets/b23235b2-26c1-4aef-bdac-19fe50dee2cd)
![img4](https://github.com/user-attachments/assets/28b3f7ca-e8dc-4d23-b71f-ba69ed537da7)
- Save by pressing s
![img5](https://github.com/user-attachments/assets/9f900540-47a4-4119-bff0-44c9f18dd44a)



- update the code `main/my_project.c` 
```bash
#include <stdio.h>
void app_main(void)
{
    printf("hello World!");
}
```
```bash
idf.py build
```

---

## **Step 7: Flash and Monitor the ESP32**

### **Flash the ESP32:**

On Linux:
- Plug in your ESP32 board to your computer.
- Check available serial ports: Open a terminal and run the following command:

```bash
```
You should see a list of devices.
```bash
```

### **Monitor the Serial Output:**

To monitor the output of the ESP32:
```bash
```

---
