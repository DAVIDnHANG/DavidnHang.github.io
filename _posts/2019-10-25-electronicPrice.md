---
column1 = dbc.Col\
(
    [
        dcc.Markdown(  """## Insights""" ),
        html.Div(children='''Let knock out all weight that more than 100 pounds. More than 100 pounds means that
        those machine are for buisness uses, or a set of electronic that comes together. 
        What weights between 0-15 lbs that $1000? a panasonic Lumix camera, gotta take 
                those baby pictures. You dont like baby pictures, how about (8 x 16gb) ram 128 gb total 
                to make 4 million rows to process a little bit faster while doing data science work? 
                 What weights 20-40 pounds that cost more than 1.5k? I need a 4000 dollars tv to prevent myself from seeing ghosts
                 cause by the New england Patriod defense on Monday while I waiting for this project to load. 
                 How about the last section? laser printer 60-100 pounds that ranges 500 5k. So this scatter is a good sample size
                 to match real world. '''),
        html.Div(children=''' There like 4 merchant that are listed more than 100 times. Bestbuy, bhphotovideo, walmart, and beach Camera.
        So let combined all other merchant and put it under other and leave those 4 be.  This merchant column rewritten can be transformed into  One Hot encoder,'''),
        html.Div(children=''' Last, Date placed on shelfs, and Date last seen will be engineer into a new feature called how long has it been on stock.
        So since beginning of it being stock, until the column seen will create a new column such that it has less than 6 months, between 6 month and 1 year and 6 months,
        and more than two years. '''),
    ],
    md=4,
)


column2 = dbc.Col\
(
    [
        html.Img(src='assets/KnockOutOneHundred.PNG', className='img-fluid'),
        html.Img(src='assets/WeightXPrice.PNG', className='img-fluid'),
        html.Img(src='assets/Merchant.PNG', className='img-fluid'),
    ]
)

layout = dbc.Row([column1, column2])
