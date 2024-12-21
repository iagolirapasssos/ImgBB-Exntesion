# ImgBB-Exntesion
The ImgBB Image Uploader Extension allows users to upload images to ImgBB directly from their MIT App Inventor projects.

#### **Project Overview**
The **ImgBB Image Uploader Extension** allows users to upload images to [ImgBB](https://imgbb.com/) directly from their MIT App Inventor projects. This extension provides an easy and asynchronous method to interact with the ImgBB API, making it simple for users to integrate image upload functionality into their apps.

---

### **Features**
1. **Asynchronous Image Upload**: Non-blocking image upload process.
2. **Event Handling**: Events triggered upon successful upload or error occurrence.
3. **Customizable Parameters**: Users can specify the file path and API key.

---

### **Installation**

1. **Download the Extension**:
   - Download the `ImgBB.aix` file from this repository.
   
2. **Import the Extension**:
   - Open your MIT App Inventor project.
   - Navigate to the **Extensions** section in the left menu.
   - Click **Import Extension** and upload the `ImgBB.aix` file.

3. **Add the Extension to Your Project**:
   - Drag and drop the ImgBB component from the Extensions palette to your project.

---

### **Example Usage**

#### **Step 1: UI Setup**
Create a basic UI with the following components:
- A **Button** to upload the image.
- A **TextBox** to input the API key.
- A **File Picker** or a **TextBox** to provide the image file path.
- A **Label** to display the upload status.

#### **Step 2: Blocks Implementation**
1. Use the `ImgBB` extension block `UploadImageToImgBB` to call the upload function.
2. Handle the events `ImageUploaded` and `ErrorOccurred` to display the result.

#### **Block Example**
Here’s how to set up the blocks in MIT App Inventor:

- **Upload Image Button Logic**:
   ```plaintext
   When Button1.Click
      Call ImgBB.UploadImageToImgBB
         Set ImagePath to TextBoxImagePath.Text
         Set ApiKey to TextBoxApiKey.Text
   ```

- **Handle Success Event**:
   ```plaintext
   When ImgBB.ImageUploaded(responseContent)
      Set LabelStatus.Text to "Upload Successful! Response: " + responseContent
   ```

- **Handle Error Event**:
   ```plaintext
   When ImgBB.ErrorOccurred(errorMessage)
      Set LabelStatus.Text to "Error: " + errorMessage
   ```

---

### **Key Configuration**

#### **Required Permissions**
Ensure the following permissions are added to your AndroidManifest.xml:
```xml
<uses-permission android:name="android.permission.INTERNET" />
```

#### **API Key**
To use this extension, you need an API key from ImgBB. Sign up on [ImgBB](https://imgbb.com/) to obtain your key.

---

### **Example Workflow**
1. Enter your ImgBB API Key in the TextBox.
2. Specify the full file path to the image (e.g., `/storage/emulated/0/DCIM/image.jpg`).
3. Tap the Upload button.
4. Monitor the Label for success or error messages.

---

### **Troubleshooting**
1. **Invalid API Key**:
   - Ensure your API key is correct.
2. **File Not Found**:
   - Verify the image file path.
3. **No Internet**:
   - Check your internet connection.

---

### **License**
This extension is open-source and distributed under the MIT License.

---

Feel free to use and adapt this extension in your projects! For any issues or contributions, submit them via GitHub's Issues tab.
