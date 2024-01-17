# explorando.R
Explorando a base de dados dslabs (homicídios nos EUA) com o R. Uma análise a partir de gráficos e tabelas.

library(dslabs)

data(murders)

str(murders)

region = murders$region

names(murders)

length(region)

total = murders$total

region = reorder(region, total, FUN = sum)

levels(region)

# classificou do menor para o maior

record = list(name = "John Doe",
               student_id = 1234,
               grades = c(95, 82, 91, 97, 93),
               final_grade = "A")

state=murders$state

class(state)

mat = matrix(1:12, 4, 3)

print(mat)

mat[2, 3]

mat[2, ]

head(murders)

abb = murders$abb

help(levels)

length(region)

length(levels(region))

levels(region)

table(murders$region)

codes = c(italy = 380, canada = 124, egypt = 818)

class(codes)

names(codes)

y = 1:10

class(y)

codes[2]

h = as.character(y)

class(y)

temperatures = c(35, 88, 42, 84, 81, 30)

cities = c('Beijing', 'Lagos', 'Paris', 'Rio de Janeiro', 'San Juan', 'Toronto')

names(temperatures) = cities

print(temperatures)

temperatures[1:3]

temperatures[c('Paris', 'San Juan')]

de_doze_a_setenta_e_três = 12:73

print(de_doze_a_setenta_e_três)

lista_de_n_impares_menores_que_cem = seq(1,99, by = 2)

print(lista_de_n_impares_menores_que_cem)

# Criando uma lista de números especificada, mas sem o seq e o lenght 
n = 0
g = 6

sequencia_dois = numeric()

while (g <= 55) {
  sequencia_dois = append(sequencia_dois, g)
  n = n + 1
  g = 6 + n * (4/7)
}

print(sequencia_dois)

# Criando uma lista de números especificada, com o seq e o lenght, pelo CHATGPT

# Parâmetros
inicio <- 6
limite <- 55
incremento <- 4/7

# Criar a sequência usando seq
sequencia <- seq(inicio, limite, by = incremento)

# Quantidade de números na sequência
quantidade_numeros <- length(sequencia)

print(sequencia)
print(quantidade_numeros)

class(sequencia)

a <- seq(1, 10)
class(a)

a <- seq(1, 10, 0.5)

# Assigning 1 to 'a'
a <- 1

# Checking the class of 'a'
class_a <- class(a)

# Assigning 1L to 'b'
b <- 1L

# Checking the class of 'b'
class_b <- class(b)

# Displaying the classes
print(class_a)
print(class_b)

x <- c("1", "3", "5")
class(x)

x = as.integer(x)
print(x)


sort(total)

index <- order(total)
total[index]

order(total)

murders$abb[index]

max(total)

i_max = which.max(total)
state[i_max]

pop = murders$population

pop = sort(pop)

min(pop)

smallest_pop = pop[1]

print(smallest_pop)

smallest_pop = order(pop)[1]

i_min = which.min(murders$population)
state_min_pop = state[i_min]
print(state_min_pop)

city_temp = data.frame(temperatures = temperatures)
print(city_temp)

data("na_example")  
str(na_example)

avarege = mean(na_example)

ind = is.na(na_example)

num_nas = sum(ind)

print(num_nas)

avarage_no_na = mean(na_example[!is.na(na_example)])

print(avarage_no_na)

state[which.max(murders$population)]

help("which.max")

pop = murders$population

murders_rate = total/pop * 100000

order_rate_murders = state[order(murders_rate)]

temp_celsios = (temperatures-32)*5/9
print(temp_celsios)

avarage_murder_rate = mean(murders_rate)

print(avarage_murder_rate)

ind <- murders_rate <= 0.71

state[ind]

west <- murders$region == "West"
safe <- murders_rate <= 1

ind <- safe & west
murders$state[ind]

ind <- which(murders$state == "California")
murders_rate[ind]

ind <- match(c("New York", "Florida", "Texas"), murders$state)
ind

murders_rate[ind]

c("Boston", "Dakota", "Washington") %in% murders$state

low = murders_rate < 1

ind = which(low)

state[ind]

northeast_low_murder_rate = state[region == "Northeast" & low]
northeast_low_murder_rate

state_low_avarange = state[murders_rate<avarage_murder_rate]
state_low_avarange

length(state_low_avarange)

cu = match(c("AK", "MI", "IA"), murders$abb)
co = state[cu]
co

testc = c("MA", "ME", "MI", "MO", "MU") %in% murders$abb
testc

plot(total, murders_rate)

plot(pop/10^6, total)

with(murders, plot(population, total))

x <- with(murders, murders_rate)
hist(x)

boxplot(murders_rate~region, data = murders)

plot(log10(total), log10(murders_rate))

hist(pop/10^6)

boxplot(pop~region, data = murders)
     ![image](https://github.com/Luiz-Fernando-Oliveira/explorando.R/assets/156798656/8662d80a-f926-4907-b006-962d85677669)
     ![image](https://github.com/Luiz-Fernando-Oliveira/explorando.R/assets/156798656/74f59630-77e0-454e-b7ee-2aee21478bfb)
     ![image](https://github.com/Luiz-Fernando-Oliveira/explorando.R/assets/156798656/38a0ddf3-7673-46c3-9e45-82dcf0fcb6a1)


