App Collection
=====================

Made by [![Appus Studio](https://github.com/alexey-kubas-appus/AppCollection/blob/master/AppCollection/Resources/appus.png)](https://appus.software)

"App Collection" show list of applications from iTunes with details.


![App Collection: Show list of applications from iTunes with details](https://github.com/alexey-kubas-appus/AppCollection/blob/master/AppCollection/Resources/IMG_7827.png)
![App Collection: Show list of applications from iTunes with details](https://github.com/alexey-kubas-appus/AppCollection/blob/master/AppCollection/Resources/IMG_7828.png)

#Setup
```Ruby
pod 'AppCollection', :git => 'https://github.com/alexey-kubas-appus/AppCollection.git'
```

```swift

import AppCollection

// Declare vc
var appCollectionVc : AppsViewController?

override func viewDidLoad() {
    super.viewDidLoad()

	// Init
	self.appCollectionVc = AppsViewController.sharedAppsViewController()
	// Set list of application ids, also application details can be fetched from file with ids, from file with ids by url and by developer id
	self.appCollectionVc?.type = .array(["858525203","578979413","919087726","507125352","642665353",
                                    "664457128","1023583941", "849600010","640097569","875063456"])
        
	// Set star image for rating
	SettingsManager.shared.filledRatingImage = UIImage(named: "StarEmpty")
	SettingsManager.shared.emptyRatingImage = UIImage(named: "StarFull")

	// Configure UI style        
	SettingsManager.shared.textColor = UIColor.green
	// Hide cancel button if vc will be pushed
	SettingsManager.shared.cancelButtonHidden = true
}

// Push vc
@IBAction func showApplicationListClicked(_ sender: Any) {
        self.navigationController?.pushViewController(self.appCollectionVc!, animated: true)
}
```

Developed By
------------

* Ilya Borshchov, Vladimir Grigoriev [Appus Studio](https:appus.software)

License
--------

Copyright 2015 [Appus Studio](https:appus.software).

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
