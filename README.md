# [Firebase] Upload Image to Firebase Storage Swift
Add your **GoogleService-Info.plist** to project and then run

[Download a configuration file for your iOS app](https://support.google.com/firebase/answer/7015592?hl=en#ios)


just call this `func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [String : Any])`

    if let pickedImage = info[UIImagePickerControllerEditedImage] as? UIImage {
    let path = "YourFilePath\YourFileName" //replace this line as per your file structure.
		PostServiceFireBase.create(for: pickedImage, path: path) { (imageURL) in
			guard let imageURL = imageURL else {
				print("Image url not found")
				return
			}
			let urlString = imageURL
			print("image url :: \(urlString)")
		}
	}
  
  and copy [FirebaseBaseServices](https://github.com/shaharukhs/FirebaseUploadImageSwift/tree/master/fireBaseUploadImage/Model/FireBaseServices) to your project
