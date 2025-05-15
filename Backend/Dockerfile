# Étape 1: Utiliser l'image JDK pour compiler le code
FROM eclipse-temurin:21-jdk-alpine as build

# Copier le fichier source Main.java dans le conteneur
COPY Main.java /usr/src/Main.java

# Définir le répertoire de travail
WORKDIR /usr/src

# Compiler le fichier Java
RUN javac Main.java

# Étape 2: Utiliser l'image JRE pour exécuter le programme compilé
FROM eclipse-temurin:21-jre-alpine

# Copier le fichier compilé Main.class du premier stage
COPY --from=build /usr/src/Main.class /usr/src/Main.class

# Définir le répertoire de travail
WORKDIR /usr/src

# Exécuter le programme Java
CMD ["java", "Main"]
