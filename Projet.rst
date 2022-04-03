

    import pandas as pd
    import numpy as np
    import matplotlib.pyplot as plt
    import seaborn as sns

    df = pd.read_csv("/content/data (12).csv")


    p = df.iloc[: , 1:]
    p1 = p.iloc[:,0:24]
    p2 = p.iloc[:,24:48]
    p3 = p.iloc[:,48:72]
    p4 = p.iloc[:,72:]
    
    p.shape ,p1.shape, p2.shape, p3.shape, p4.shape

----------------------------------------------------------------

   
    plt.style.use('ggplot')
    ncols1 = 3
    nrows1 = int(np.ceil(len(p1.columns) / (1.0*ncols1)))
    fig, axes = plt.subplots(nrows=nrows1, ncols=ncols1, figsize=(150, 150))
    
    counter = 0
    for i in range(nrows1):
      for j in range(ncols1):
            ax = axes[i][j]
    
            if counter < len(p1.columns):
    
                ax.hist(p1[p1.columns[counter]], color='Blue', alpha=0.9, label='{}'.format(p1.columns[counter]))
                ax.set_xlabel(str(p1.columns[counter]), fontsize=60)
                ax.set_ylabel('Count', fontsize=10)
                ax.set_yscale('log')

            else:
                ax.set_axis_off()
    
            counter += 1
    fig1 = plt.gcf()
    plt.show()
    fig1.savefig("PP1.png")


    ncols2 = 4
    nrows2 = int(np.ceil(len(p2.columns) / (1.0*ncols2)))
    fig, axes = plt.subplots(nrows=nrows2, ncols=ncols2, figsize=(100, 100))
    
    counter = 0
    for i in range(nrows2):
      for j in range(ncols2):
            ax = axes[i][j]
    
            if counter < len(p2.columns):
                ax.hist(p2[p2.columns[counter]], color='blue', alpha=1, label='{}'.format(p2.columns[counter]))
                ax.set_xlabel(str(p2.columns[counter]), fontsize=50)
                ax.set_ylabel('Count', fontsize=10)
                ax.set_yscale('log')
    
            else:
                ax.set_axis_off()
    
            counter += 1
    
    
    fig2 = plt.gcf()
    plt.show()
    fig2.savefig("PP2.png")


    ncols3 = 4
    nrows3 = int(np.ceil(len(p3.columns) / (1.0*ncols3)))
    fig, axes = plt.subplots(nrows=nrows3, ncols=ncols3, figsize=(100, 100))
    
    counter = 0
    for i in range(nrows3):
      for j in range(ncols3):
            ax = axes[i][j]
    
            if counter < len(p3.columns):
                ax.hist(p3[p3.columns[counter]],color='blue', alpha=1, label='{}'.format(p3.columns[counter]))
                ax.set_xlabel(str(p3.columns[counter]), fontsize=50)
                ax.set_ylabel('Count', fontsize=10)
                ax.set_yscale('log')
                leg = ax.legend(loc='upper left')
                leg.draw_frame(False)
    
            else:
                ax.set_axis_off()
    
            counter += 1
    fig3 = plt.gcf()
    plt.show()
    fig3.savefig("P3.png")


    ncols4 = 4
    nrows4 = int(np.ceil(len(p4.columns) / (1.0*ncols4)))
    fig, axes = plt.subplots(nrows=nrows4, ncols=ncols4, figsize=(100, 100))
    
    counter = 0
    for i in range(nrows4):
      for j in range(ncols4):
            ax = axes[i][j]
    
            if counter < len(p4.columns):
    
                ax.hist(p4[p4.columns[counter]],color='blue', alpha=1, label='{}'.format(p4.columns[counter]))
                ax.set_xlabel(str(p4.columns[counter]), fontsize=50)
                ax.set_ylabel('Count', fontsize=10)
                ax.set_yscale('log')
                leg = ax.legend(loc='upper left')

            else:
                ax.set_axis_off()
    
            counter += 1
    
    fig4 = plt.gcf()
    plt.show()
    fig4.savefig("P4.png")