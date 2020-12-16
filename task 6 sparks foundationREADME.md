# Task-6-Prediction-using-Decision-Tree-Algorithm-
Prediction using Decision Tree Algorithm 
###Create the Decision Tree classifier and visualize it graphically. 
###The purpose is if we feed any new data to this  classifier, it would be able to predict the right class accordingly
#KRISHAN GOPAL SHARMA

library("rpart")
library("dplyr")
library(rpart.plot)
indexes = sample(150)
#partion of data
iris_train = iris[indexes,]
iris_test = iris[indexes, ]
target = Species ~ Sepal.Length + Sepal.Width + Petal.Length + Petal.Width
##decision tree with rpart
tree = rpart(target, data = iris_train, method = "class")
rpart.plot(tree)
library(tidyverse)
library(caret)
library(rpart)
model <- rpart(Species ~., data = iris)
par(xpd = NA)
#predicition from model for particular class finding
newdata <- data.frame(Sepal.Length = 6.5, Sepal.Width = 3.0,Petal.Length = 5.2, Petal.Width = 2.0)
model %>% predict(newdata, "class")
