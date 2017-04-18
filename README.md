# Exploratory-Data
+getData <- function(path) {
 +    header <- colnames(read.table(path, header = TRUE, sep = ";", nrows = 0))
 +    rows <- read.table(path, sep = ";", dec = ".", na.strings= "?", skip = 66637, nrows = 69517-66637)
 +    colnames(rows) <- header
 +    rows$Date <- strptime(paste(rows$Date, rows$Time, sep = " "), "%d/%m/%Y %H:%M:%S")
 +    return(rows)
 +}
 +
 +plot1 <- function(path) {
 +    data <- getData(path)
 +    png("plot1.png")
 +    hist(data$Global_active_power, col = "red", main = "Global Active Power", xlab = "Global Active Power (kilowatts)")
 +    dev.off()
 +} 
 
