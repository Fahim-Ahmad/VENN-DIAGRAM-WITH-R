# VENN DIAGRAM WITH R

```
# install.packages("VennDiagram")
library(VennDiagram)
```

### Generate a data frame with 3 columns of 150 random words

```
set.seed(10000)

df <- data.frame(
  set_1 = paste(rep("word" , 150) , sample(c(1:1000) , 150 , replace=F) , sep=" "),
  set_2 = paste(rep("word" , 150) , sample(c(1:1000) , 150 , replace=F) , sep=" "),
  set_3 = paste(rep("word" , 150) , sample(c(1:1000) , 150 , replace=F) , sep=" ")
)

sum(df$set_1 %in% df$set_2) # 26
sum(df$set_1 %in% df$set_3) # 25
sum(df$set_2 %in% df$set_3) # 24
```

### creating a simple Venn diagram, the output will be in the working directory

```
venn.diagram(
  x = df,
  filename = "venn_diagram_1.png"
)
```

![](venn_diagram_1.png)

### change line wide, line type, line color, and circle colors

```
venn.diagram(
  x = df,
  filename = "venn_diagram_2.png",

  lwd = 2,# line wide
  lty = 'dotted', # line type. Use "blank" to remove the line
  col="#21908dff", # line color
  fill = c("Red", "Orange", "steelblue"), # circle colors
)
```
![](venn_diagram_2.png)

### customize labels size, labels distance from the circle, and labels positions

```
venn.diagram(
  x = df,
  filename = 'venn_diagram_3.png',
  
  lwd = 2,# line wide
  lty = 'dotted', # line type. Use "blank" to remove the line
  col="#21908dff", # line color
  fill = c("Red", "Orange", "steelblue"), # circle colors
  
  cex = 1, # numbers size
  fontface = "bold", # bold numbers
  
  cat.cex = 1.5, # labels size
  cat.fontface = "bold", # bold labels
  cat.dist = c(0.08, 0.08, 0.1), # labels distance from the diagram
  cat.default.pos = "outer", # default is "outer", change it to "text" to have the labels inside the circles
)  
```

![](venn_diagram_3.png)

### change labels names

```
venn.diagram(
  x = df,
  filename = 'venn_diagram_4.png',
  
  category.names = c("First set" , "Second set" , "Third set"), # change labels names
  
  lwd = 2,# line wide
  lty = 'dotted', # line type. Use "blank" to remove the line
  col="#21908dff", # line color
  fill = c("Red", "Orange", "steelblue"), # circle colors
  
  cex = 1, # numbers size
  fontface = "bold", # bold numbers
  
  cat.cex = 1.5, # labels size
  cat.fontface = "bold", # bold labels
  cat.dist = c(0.08, 0.08, 0.1), # labels distance from the diagram
  cat.default.pos = "outer" # default is "outer", change it to "text" to have the labels inside the circles
)
```
![]("venn_diagram_4.png")

