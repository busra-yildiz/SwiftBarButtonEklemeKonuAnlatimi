# SwiftBarButtonEklemeKonuAnlatimi
Swift dilinde iOS uygulamalarında UIBarButtonItem kullanarak bar button eklemek oldukça yaygındır. Bar buttonlar, kullanıcı arabirimindeki belirli
eylemleri tetiklemek veya gezinme işlemlerini gerçekleştirmek için kullanılır. Bu bar buttonlar, genellikle bir UINavigationBar içinde veya bir UIToolbar 
içinde bulunur. İşte UIBarButtonItem'ı kullanarak bir bar button eklemenin adımları:

Bar Button Oluşturma:
Bar buttonları oluşturmadan önce ne tür bir bar button eklemek istediğinize karar vermelisiniz. İki temel türü vardır:
Sistem Bar Buttonları: Ön tanımlı simgeler veya metinler kullanılarak oluşturulurlar ve genellikle yaygın kullanılan işlemleri temsil ederler. Örneğin, 
geri gitmek için kullanılan "Geri" veya "Paylaş" düğmeleri.
Özel Bar Buttonlar: Kendi özel görünümünüzü veya davranışınızı temsil etmek için oluşturulan özel bar buttonlardır. Genellikle özel bir görüntü veya metin 
içerebilirler.
Aşağıda her iki tür için de bir örnek bulunmaktadır:
// Sistem Bar Buttonu örneği
let backButton = UIBarButtonItem(title: "Geri", style: .plain, target: self, action: #selector(goBack))

// Özel Bar Buttonu örneği
let customButton = UIBarButtonItem(image: UIImage(named: "custom-icon"), style: .plain, target: self, action: #selector(customAction))

Bar Button'ı Ekleme:
Şimdi oluşturduğunuz bar buttonları eklemek istediğiniz navigasyon çubuğu veya araç çubuğu içine yerleştirmeniz gerekiyor. Bu, genellikle bir
UINavigationItem veyaUIToolbar nesnesinin özelliklerini güncellemeyi gerektirir. Aşağıda bir örnek bulunmaktadır:
// Sistem Bar Button'ını eklemek
navigationItem.leftBarButtonItem = backButton // Geri butonunu sol tarafta göster

// Özel Bar Button'u eklemek
let flexibleSpace = UIBarButtonItem(barButtonSystemItem: .flexibleSpace, target: nil, action: nil)
let fixedSpace = UIBarButtonItem(barButtonSystemItem: .fixedSpace, target: nil, action: nil)
fixedSpace.width = 16 // Özel boşluk eklemek için

toolbar.setItems([flexibleSpace, customButton, fixedSpace], animated: false)


Bar Button Eylemlerini Tanımlama:
Bar buttonların tıklanma eylemlerini belirlemek için target ve action parametrelerini kullanırsınız. target, eylemin hangi nesneyi çağırması gerektiğini
belirtir, action ise çağrılacak metodu gösterir. Örnek olarak:
@objc func goBack() {
    // Geri gitme eylemini burada tanımla
}

@objc func customAction() {
    // Özel eylemi burada tanımla
}

Bu adımları takip ederek, bir UIBarButtonItem ekleyebilirsiniz. Bar buttonlar, kullanıcılarınızın uygulamanızdaki eylemleri gerçekleştirmelerine 
olanak sağlar ve kullanıcı arayüzünüzü zenginleştirebilir.



