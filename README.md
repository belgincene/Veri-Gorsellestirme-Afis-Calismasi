#Afiş çalışması
# Gerekli paketlerin yuklenmesi
install.packages("ggplot2")
install.packages("GGally")
library(ggplot2)
library(GGally)
# Veri setinin yuklenmesi
url <- "https://vincentarelbundock.github.io/Rdatasets/csv/ggplot2/diamonds.csv"
diamonds <- read.csv(url)
head(diamonds)
# Grafiklerin olusturulmasi
# Karat, Fiyat değişiminin Kesim Kriterine Göre Dağılımı
ggplot(diamonds, aes(x = carat, y = price, color = cut)) +
geom_point(alpha = 0.5) +
theme_minimal() +
labs(title = "Karat Fiyat değişiminin Kesim Kriterine Göre Dağılımı", x = "Karat", y = "Fiyat (USD)") +
scale_color_brewer(palette = "Blues")
# Kesim (Cut) ve Fiyat Box Grafik
ggplot(diamonds, aes(x = cut, y = price, fill = cut)) +
geom_boxplot() +
theme_minimal() +
labs(title = "Kesime Göre Fiyat Değişimi", x = "Kesim", y = "Fiyat (USD)") +
scale_fill_brewer(palette = "Blues")
# Renk ve Fiyat Violin Grafik
ggplot(diamonds, aes(x = color, y = price, fill = color)) +
geom_violin() +
theme_minimal() +
labs(title = "Renklere Göre Fiyat Değişimi", x = "Renk", y = "Fiyat (USD)") +
scale_fill_brewer(palette = "Blues")
# Berraklik ve Fiyat Box Grafik
ggplot(diamonds, aes(x = clarity, fill = clarity)) +
geom_bar() +
theme_minimal() +
labs(title = "Berraklığa Göre Fiyat Değişimi ", x = "Berraklık", y = "Fiyat (USD)") +
scale_fill_brewer(palette = "Blues")
