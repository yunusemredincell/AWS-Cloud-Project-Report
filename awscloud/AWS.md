# **AWS Bulut Projesi Raporu**

### AWS Bulut Projesi Raporu, AWS servislerine neden ihtiyaç olunduğunu, AWS servislerini kullanarak oluşturulmuş bir bulut sisteminin nasıl çalıştığını, ne gibi gereksinimlerin

### olduğunu, hangi aşamalardan geçildiğini detaylı şekilde açıklayarak kullanıcıların kullanım kolaylığı elde etmesi için hazırlanmıştır.

## **AWS (_Amazon Web Services_) nedir?**

### Amazon Web Servisleri, Amazon tarafından hizmete sunulmuş, isteğe bağlı bulut bilişim servis modelleri (IaaS,PaaS,SaaS) ve uygulama programlama arayüzleri (API) gibi servisleri

### sağlayan bir bulut servisidir. Temmuz 2002 tarihinde kullanıma sunulmuş olup, kullandıkça öde prensibiyle bireysel kullanıcılara, kurumsal şirketlere bulut bilişim hizmetleri

### tesis etmektedir. Ayrıca çeşitli temel altyapı hizmetleri ve dağıtılmış bilgi işlem altyapı hizmetleri sağlamaktadır. AWS teknolojisi dünya genelinde sunucu çiftliklerine

### dağıtılarak kullanıma sürülür. Abonelik modellerine göre seçilen donanım, işletim sistemi, kullanım miktarı, veri depolama, veri gizliliği ve güvenliği opsiyonlarına göre

### fiyatlandırma vardır.

## **Amazon Web Servisleri nasıl kullanılır?**

### Amazon web servisleri, aws.amazon.com üzerinden ücretsiz kaydolunarak kullanılabilir. Ek 1 de gözüktüğü gibi geçerli bir e-posta adresi ve oluşturacağınız kullanıcı adı ile

### kullanıma başlanabilir.

![This is an alt text.](image\ek1.png "EK 1")

#### _Ek 1_

### Kaydolduktan sonra giriş kısmında bulunan Console Home sekmesinden son kullandığınız servisleri, elde ettiğiniz gelirleri görüntüleyebilir, arama kısmından kullanacağınız

### servislere erişebilirsiniz. Ayrıca Ek 2’de görüldüğü gibi Welcome to AWS kısmından AWS kullanımıyla ilgili başlangıç seviyesinde bilgilere erişerek hızlıca kullanıma

### başlayabilirsiniz.

![This is an alt text.](image\ek2.png "EK 2")

#### _Ek 2_

## **AWS ile Kendi Bulut Sisteminizi oluşturma**

### Amazon Web Servisleri ile kendi bulut sisteminizi oluşturmanız için AWS’ in bazı servislerini kullanmanız gerekmektedir. Temel olarak 5 ayrı servis kullanacağımız projede,

### öncelikli olarak bu servislerin ne olduğunu, kendi içlerinde nasıl gereklilikleri olduğu ve nasıl kullanıldıklarını ele alacağız. Bu 5 servis şu şekildedir: AWS Amplify, API

### Gateway, Lambda, IAM (Identity and Access Management) ve DynamoDB.

## **Bulut Projesi’nin Mimarisi**

### Bulut Projesini oluştururken dikkat edilmesi gereken en önemli hususlardan biri kullanılacak servislerin birbirileriyle olan entegrasyonu ve çalışma sistemlerindeki devamlılığı

### sağlayan mimarilerdir. Projemizde oluşturulan web sitesi için gerekli olan servislerin birbirleriyle olan ilişkileri Şekil 1’deki gibidir. Tüm bu servislerin doğru çalışması için

### birbirleriyle olan bağlantılar ve ne için gerekli oldukları ileriki bölümlerde detaylıca ele alınacaktır.

![This is an alt text.](image\arch.jpg "ŞEKİL 1")

#### _Şekil 1_

## **AWS Amplify**

### AWS Amplify, ön uç web ve mobil geliştiricilerinin, kullanım örnekleri geliştikçe AWS hizmetlerinin genişliğinden yararlanma esnekliğiyle AWS üzerinde tam yığın uygulamalarını

### kolayca oluşturmasına, göndermesine ve barındırmasına olanak tanıyan eksiksiz bir çözümdür. Bulut uzmanlığı gerektirmeden kendi web servislerinizi, mobil uygulamalarınızı

### kolayca kullanmaya olanak tanır. Projemizde bir web sitesi üzerinden işlem yapacağımızı düşünürsek, web sitesi kaynak kodlarını AWS Amplify’ a yükleyerek kullanıma başlanabilir.

![This is an alt text.](image\ek3.png "EK 3")

#### _Ek 3_

### Ek 3’te bulunan New App kısmından Host Web App seçilerek projenizin kaynak kodu için açılan sekmeden hangi yolla kaynak kodlarınızı yükleyeceğinizi seçmeniz gerekir. (_Hosting Page_)

![This is an alt text.](image\hosting.png "HOSTING PAGE")

#### _Hosting Page_

### GitHub üzerinden yüklemeyi seçtiğimizi varsayarsak aktif olarak bulunan bir GitHub hesabını AWS ile eş zamanlayarak projenizi GitHub üzerinden yükleyebilirsiniz. Herhangi bir git ,

### sağlayıcısı kullanmak istemezseniz Deploy without Git provider seçeneğiyle kaynak kodlarınızı zipleyerek ya da bilgisayarınızdan dosya halinde sürükleyerek yükleme yapabilirsiniz.

### Yükleme tamamlandıktan sonra projeniz App kısmında Ek 4’teki gibi gözükmelidir.

![This is an alt text.](image\ek4.png "EK 4")

#### _Ek 4_

### Domain kısmındaki linkte kaynak kodlarıyla (HTML,CSS,Javascript) oluşturmuş olduğunuz web sitesinin kendisi bulunmaktadır. (Ek 5.)

![This is an alt text.](image\ek5.png "EK 5")

#### _Ek 5_

### Bir sonraki adımda Lambda servisini kullanarak web sitesi için gerekli olacak fonksiyonları kullanıma hazır hale getireceğiz.

## **Lambda**

### AWS Lambda, sunucu tedarik etmeden veya yönetmeden neredeyse her tür uygulama veya arka uç hizmeti için kod çalıştırmanıza olanak tanıyan, sunucusuz, olaya dayalı bir işlem

### hizmetidir. Lambda'yı 200'ün üzerinde AWS hizmeti ve hizmet olarak yazılım (SaaS) uygulamasından tetikleyebilir ve yalnızca kullandığınız kadar ödeyebilirsiniz. Lambda’ nın

### projedeki temel kullanımı, kullanıcının girdiği kullanıcı adı ve şifreyi, içerisine eklediğimiz fonksiyon sayesinde bilgilerin alınmasına olanak tanır. Kullanım adımlarına

### gelirsek, arama kısmına Lambda yazarak servis arayüzünde bulunan Create Function seçeceğiyle fonksiyon oluşturulur. Ek 6’ da görüldüğü şekilde ayarlar yapılır.

![This is an alt text.](image\ek6.png "EK 6")

#### _Ek 6_

### Runtime kısmında Lambda fonksiyonunu yazarken kullanacağınız programlama dili seçilir. Projeye göre Python 3.9 seçilmiştir. Diğer ayarlara dokunmadan fonksiyon oluşturulur. Yeni

### açılacak sayfada alt tarafta bulunan Code kısmına gelerek kullanıcının girdiği verileri eşleyen ve DynamoDB ile bağlantıları sağlayacak kodlar fonksiyon için yazılır. (Ek 7). Kod

### yazıldıktan sonra üst kısımda bulunan Deploy kullanılarak fonksiyon yüklenir. Test seçeneği kullanılarak alt kısımda bulunan JSON dosyası ile fonksiyonun çalışıp çalışmadığı test

### edilir. (Ek 8.) Bütün bu aşamalar tamamlandıktan sonra Lambda fonksiyonunu çağırması için bir API Gateway oluşturulur.

![This is an alt text.](image\ek7.png "EK 7")

#### _Ek 7_

![This is an alt text.](image\ek8.png "EK 8")

#### _Ek 8_

## **API Gateway**

### Application Programming Interface (API), bir yazılımın başka bir yazılımla tanımlanmış işlevlerinin kullanılabilmesi için oluşturulmuştur. Projede web sitesinde istemci ile sunucu

### arasındaki iletişim için kullanılmaktadır. Amazon API Gateway ise, yazılım geliştiriciler tarafından istenen ölçekte API yayımlanmasını, API’lerin izlenmesini, bakımının

### yapılmasını, güvenliğinin sağlanmasını ve çalıştırılmasını mümkün kılan, tam olarak yönetilen bir hizmettir. API’leri uygun ölçekte güvenli ve güvenilir bir şekilde çalıştırmak

### için gereken tüm kaçınılmaz ağır yüklerin üstesinden gelen bir kullandıkça öde hizmetidir. Amazon API Gateway’i kullanmak için servisi AWS üzerinden açmak gerekmektedir. Açtıktan

### sonra Create API seçilir. Ardından REST API (Public) seçilir. Ardından açılan sayfada Ek 9 da görüldüğü şekilde ayarlamalar yapılır.

![This is an alt text.](image\ek9.png "EK 9")

#### _Ek 9_

### Daha sonrasında oluşturulan API içerisinden _Create Method_ seçilir ve POST metodu oluşturulur. (Ek 10.) Tüm bu aşamalardan sonra Ek 11’deki şema elde edilir. Bu işlemlerin ardından

### _Actions_ kısmından _Enable CORS_ seçeneğindeki adımlar tamamlanır. Bunun ardından Deploy API seçilerek bir _Stages_ oluşturulur.

![This is an alt text.](image\ek10.png "EK 10")

#### _Ek 10_

![This is an alt text.](image\ek11.png "EK 11")

#### _Ek 11_

### Oluşturulan Stages AWS tarafından oluşturulmuş bir URL barındırmaktadır. (Ek 12.)

![This is an alt text.](image\ek12.png "EK 12")

#### _Ek 12_

### Oluşturulan bu URL sizin API Gateway’inizi oluşturmaktadır. Amplify ile API Gateway servislerini birbirleriyle etkileşime sokmak için bu Invoke URL kullanılmaktadır. Kaynak

### kodumuzda script kısmında Ek 13’teki gibi Invoke URL kullanılarak Amplify ile API Gateway servisleri bağlanır.

![This is an alt text.](image\ek13.png "EK 13")

#### _Ek 13_

## **DynamoDB**

### Amazon DynamoDB, her ölçekte yüksek performanslı uygulamaları çalıştırmak için tasarlanmış, tam olarak yönetilen, sunucusuz, anahtar-değer NoSQL veri tabanıdır. DynamoDB; yerleşik

### güvenlik, sürekli yedeklemeler, otomatikleştirilmiş çok Bölgeli çoğaltma, bellek içi önbelleğe alma, içeri ve dışarı veri aktarma araçları sunar. DynamoDB servisine giderek, Create

### Table komutuyla DynamoDB oluşturulur. Bu sayede Lambda fonksiyonundan sonra oluşan veriler DynamoDB ile veri tabanında depolanır. Bunun yapılması için IAM üzerinden gerekli

### izinlerin ve erişimin sağlanması için DynamoDB ile oluşturulan Amazon Resource Name (ARN) kopyalanır (Ek 14) ve gerekli konfigürasyonlar için kullanılır.

![This is an alt text.](image\ek14.png "EK 14")

#### _Ek 14_

## IAM (_Identity and Access Management_)

### IAM ile ayrıntılı izinler belirleyerek kimin neye erişebileceğini tanımlarsınız. IAM daha sonra, her istek için bu izinleri uygular. Erişim varsayılan olarak reddedilir ve yalnızca

### izinlerde "İzin Ver" komutu varsa erişim sunulur. Bulut projesinde gerekli izinlerin sağlanabilmesi için Lambda servisi ile _Configurations_ kısmına gelinir. Ardından sol tarafta

### bulunan _Permissions_ seçeneğine tıklanarak _Execution Role_ seçeneğine gidilir. Burada açılan sayfa ile _Add Permission_ ardından _Create Inline Policy_ seçeneğiyle JSON dosyası

### güncellenir. (Ek 15) JSON kodunda yer alan Resource kısmına DynamoDB ile oluşturulan ARN yapıştırılır. Bu sayede DynamoDB için gerekli izinler sağlanmış olur.

![This is an alt text.](image\ek15.png "EK 15")

#### _Ek 15_

### Tüm bu adımların ardından Amplify üzerinden web sitesini çalıştırarak kullanıcı adı ve parola girilir. (Ek 16)

![This is an alt text.](image\ek16.png "EK 16")

#### _Ek 16_

### DynamoDB servisiyle _Explore Items_ seçilerek girilen şifre ve kullanıcı adı veri tabanına kaydolmuş olur. (Ek 17)

![This is an alt text.](image\ek17.png "EK 17")

#### _Ek 17_

### Tüm bu adımların ardından web sitesi kullanılarak oluşturulmuş Bulut Projesi tamamlanmış olur. AWS servislerini kullanarak bulut hizmet modeli olarak PaaS (Platform as a Service)

### ve SaaS (Software as a Service) modellerini kullanarak AWS bizim için arka planda sunucu, orta katman, ağ iletişimi, depolama gibi kısımları halleder. Buna ek olarak kendi

### yazdığımız kaynak kodlarıyla uygulama kısmını kendimiz yaptık. Büyük kolaylık sağlayan bu bulut sistemi sayesinde projemizi çalıştırmak için sanal bir ortam elde ettik.
