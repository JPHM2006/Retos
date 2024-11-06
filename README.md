# Retos 
# 1
especies <- data.frame(
  especie = c("Ajolote", "Rana", "Serpiente", "Tortuga"),
  habitat = c("Lago", "Río", "Bosque", "Lago"),
  tamano = c(30, 10, 150, 50),
  peso = c(150, 25, 1000, 500)
)


especies_lago <- especies %>%
  filter(habitat == "Lago") %>%
  arrange(desc(tamano))

print(especies_lago)

# 2
data(iris)


ggplot(iris, aes(x = Sepal.Length, y = Sepal.Width, color = Species)) +
  geom_point() +
  labs(title = "Gráfico de dispersión de Sepal.Length y Sepal.Width",
       x = "Largo del sépalo",
       y = "Ancho del sépalo")
      
# 3
calificaciones <- data.frame(
  estudiante = c("Ana", "Carlos", "Lucía", "Jorge", "Ana", "Carlos", "Lucía", "Jorge"),
  asignatura = c("Matemáticas", "Matemáticas", "Matemáticas", "Matemáticas", "Historia", "Historia", "Historia", "Historia"),
  calificacion = c(95, 85, 92, 88, 78, 82, 85, 90)
)


promedio_calificaciones <- calificaciones %>%
  group_by(estudiante) %>%
  summarise(promedio = mean(calificacion))

print(promedio_calificaciones)

# 4
alturas <- data.frame(
  nombre = c("Laura", "Pedro", "Sara", "Miguel"),
  altura_cm = c(160, 175, 150, 180)
)


alturas$altura_m <- alturas$altura_cm / 100

print(alturas)

# 5
ventas <- data.frame(
  mes = c("Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio"),
  ventas = c(12000, 15000, 13000, 16000, 17500, 14000)
)


ggplot(ventas, aes(x = mes, y = ventas)) +
  geom_bar(stat = "identity", fill = "skyblue") +
  labs(title = "Ventas mensuales", x = "Mes", y = "Ventas")

# 6
productos <- data.frame(
  producto = c("A", "B", "C", "D"),
  precio = c(20, 35, 50, 10),
  cantidad_vendida = c(100, 200, 150, 250)
)


productos$ingreso_total <- productos$precio * productos$cantidad_vendida

print(productos)


write.csv(productos, "productos.csv", row.names = FALSE)

# 7
data(mtcars)


ggplot(mtcars, aes(x = as.factor(cyl), y = mpg)) +
  geom_boxplot(fill = "lightblue") +
  labs(title = "Distribución de millas por galón según el número de cilindros",
       x = "Número de cilindros",
       y = "Millas por galón (mpg)")
