ui <- fluidPage(
  titlePanel('practice'),
  sidebarLayout(
    sidebarPanel('Sidebar Panel'),
    mainPanel('Main Panel')
  ),
  tabsetPanel(
    tabPanel("tab1",
             p("p creates a paragraph."),
             p("A new p() command starts a new paragraph. show style attribute", style = "font-family: 'times'; font-si16pt"),
             strong("strong() makes bold text."),
             em("em() creates italicized (i.e, emphasized) text."),
             br(),
             code("code displays your text similar to computer code"),
             h1('title'),
             h2('title2'),
             h3('title3'),
             br(),
             br(),
             div("div creates segments of text with a similar style. This division of text is all blue because I passed the argument 'style = color:blue' to div", style = "color:blue"),
             br(),
             p("span does the same thing as div, but it works with",
               span("groups of words", style = "color:green"),
               "that appear inside a paragraph.")
    ),
    
    tabPanel("tab2",
             img(src="picture.png",width=1000)
    ),
    tabPanel("tab3",
             plotOutput("distPlot"), 
             sliderInput("bins",
                         label = "Number of bins:",
                         min = 1,
                         max = 50,
                         value = 30))
  )
)


# 2. Server
server <- function(input,output){
  output$distPlot <- renderPlot({
    x    <- faithful$waiting
    bins <- seq(min(x), max(x), length.out = input$bins + 1)
    hist(x, breaks = bins, col = "#75AADB", border = "white",
         xlab = "Waiting time to next eruption (in mins)",
         main = "Histogram of waiting times")
  })
}

shinyApp(ui=ui, server=server)