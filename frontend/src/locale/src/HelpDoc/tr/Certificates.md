## Sertifika Yardımı

### HTTP Sertifikası

HTTP doğrulanmış bir sertifika, Let's Encrypt sunucularının
etki alanlarınıza HTTP üzerinden (HTTPS değil!) ulaşmaya çalışacağı ve başarılı olduğunda
sertifikanızı vereceği anlamına gelir.

Bu yöntem için, etki alanı(ları)nız için oluşturulmuş bir _Proxy Host_ kullanmanız gerekir
bu da HTTP üzerinden erişilebilir olmalı ve bu Nginx yüklemesine işaret etmelidir. Sertifika
verildiğinde, _Proxy Host_'u bu sertifikayı HTTPS bağlantıları için de kullanacak şekilde
değiştirebilirsiniz. Ancak, sertifikanızı yenilemek için _Proxy Host_ hala HTTP erişimi
için yapılandırılmış olması gerekecektir.

Bu işlem joker etki alanlarını (*.domaininiz.com) _desteklemez_.

### DNS Sertifikası

DNS doğrulanmış bir sertifika, bir DNS Sağlayıcı eklentisi kullanmanızı gerektirir. Bu DNS
Sağlayıcısı, etki alanınızda geçici kayıtlar oluşturmak için kullanılacak ve ardından Let's
Encrypt, sahibi olduğunuzdan emin olmak için bu kayıtları sorgulayacak ve başarılı olursa
sertifikanızı verecektir.

Bu sertifika türünü talep etmeden önce oluşturulmuş bir _Proxy Host_'a ihtiyacınız yoktur.
Ve _Proxy Host_'unuzu HTTP erişimi için yapılandırmanız gerekmez.

Bu işlem joker etki alanlarını (*.domaininiz.com) _destekler_.

### Özel Sertifika

Kendi Sertifika Otoritesi tarafından sağlanan kendi SSL Sertifikanızı yüklemek için bu
seçeneği kullanın.
