# 7 classification algorithm
rainfall <-c(799,1174.8,865.1,1334.6,635.4,918.5,685.5,998.6,784.2,985,882.8,1071)<br>
rainfall.timeseries <- ts(rainfall,start = c(2012,1),frequency = 12)<br>
print(rainfall.timeseries)<br>
png(file = "rainfall.png")<br>
plot(rainfall.timeseries)<br>
dev.off()<br>
plot(rainfall.timeseries)<br>


# 8  Clustering Algorithm
newiris <- iris<br>
newiris$Species <- NULL<br>
(kc <-kmeans(newiris,3))<br>
table (iris$Species,kc$cluster)<br>
plot(newiris[c("Sepal.Length","Sepal.Width")],col=kc$cluster)<br>

# 9 Linear regression
A. Create Relationship Model & get the Coefficients
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
relation <- lm(y~x)
print(relation)
B. Get the Summary of the Relationship
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
relation <- lm(y~x)
print(summary(relation))
C. Predict the weight of new persons
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
relation <- lm(y~x)
a <- data.frame(x = 170)
result <- predict(relation,a)
print(result)
D. Visualize the Regression Graphically
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
relation <- lm(y~x)
png(file = "linearregression.png")
plot(y,x,col = "blue",main = "Height & Weight Regression", abline(lm(x~y)),cex = 1.3,pch = 16,xlab = "Weight in Kg",ylab = "Height in cm")
dev.off()
plot(y,x,col = "blue",main = "Height & Weight Regression", abline(lm(x~y)),cex = 1.3,pch = 16,xlab = "Weight in Kg",ylab = "Height in cm")
