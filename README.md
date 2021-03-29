# CNN for handwriting recognition

Il seguente progetto è stato realizzato per la valutazione finale del corso di Machine Learning - Master in Data Science for Economics, Business and Finance 2020/2021 (Università degli Studi di Milano).

# descrizione 

Il progetto consiste nel realizzare ed allenare una ANN capace di riconoscere la scrittura manuale. 
A fine didattico si è deciso di confrontare la MLP e la CNN, inquanto questultima dovrebbe essere in grado d'identificare e riconoscere meglio insiemi di pattern geometrici come possono essere le lettere alfabetiche. 
In secondo luogo, e sempre a scopo didattico, di ridurre le dimensioni del Dataset in input per i seguenti scopi: 
- bilanciare il Dataset 
- aumentare le differenze di prestazione fra CNN e MLP 
-  studiare il miglioramento nell'apprendimento dovuto alla presenza di data augmentation layers

# Data leaning and preparation

Il dataset fornito per il progetto presenta un'insieme di 372450 lettere alfabetiche scritte a mano in stampatello, e già identate con la classe d'appartenenza (26 classi totali). 
Il controllo qualitativo sui dati è stato eseguito nei seguenti tre metodi :

- controllo " a campione" delle immagini per verificare che non ci fossero delle incongruenze fra i campioni 
- controllo dell'assenza di seamples mancanti 
- controllo della popolosità di seamples per ogni etichetta  

Il controllo sulla popolosità rivela un forte sbilanciamento che penalizza le lettere I e F. 

Il dataset è stato suddiviso in validation_set , test_set , e train_set. 

I dati sono stati successivamente scalati e normalizzati al fine di poterli usare per allenare le due ANN. 

# implementation and training of neural networks 

Ho proceduto con l'implementazione delle due reti.
La struttura della MLP è stata ottenuta impilando tre layers di diverse densità ed è stata poi usata come parte di output per la CNN al fine di poter valutare meglio il contributo dato dalla presenza dei due layer convoluzionali presenti nella CNN. 

# reducing the dataset 
Nel secondo script il dataset è stato bilanciato (e quindi snellito ) per le motivazioni elencate nella presentazione.
Allenando le reti si è ovviamente notato un netto peggioramento nella fase di apprendimento delle stesse. 
Al fine d'aumentare l'accuracy e diminuire il generalization gap ho proceduto all'aggiunta di due layer di Data Augmentation i quali hanno portato un notevole miglioramento delle prestazioni.

# data visualisation 

Al fine di visualizzare e confrontare i dati sono state plottate le confusion matrix , i grafici di conversione e gli score per ogni rete proposta. 
Al fine di poter effettivamente confrontare i dati tutte le reti sono state testate sullo stesso test_set.
