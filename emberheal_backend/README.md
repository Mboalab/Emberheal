## Backend

To run the backend, follow the steps below:

1. Install the required packages using the following command:
```bash
pip install -r requirements.txt
```

2. Run the following command to start the server:
```bash
flask run
```

3. The server will start at `http://localhost:5000/`

<br/>

---

<br/>

### API Docs :

- http://localhost:5000/ or `...5000/root` => 200 OK

- http://localhost:5000/result  => Bad Request (500)

- http://localhost:5000/transcribe  => [Body -> form-data : {Key: "file", Value: "audio_file"}] → ExampleResponse : `{"transcription":"Hello World!"}` 

- http://localhost:5000/result?sym1=cough&sym2=itching&sym3=none&sym4=none&sym5=none => [With Disease]

- Response : `{"Disease":"Fungal infection","Precaution_1":"bath twice","Precaution_2":"use detol or neem in bathing water","Precaution_3":"keep infected area dry","Precaution_4":"use clean cloths"}`


> - http://localhost:5000/d3data?sym1=cough&sym2=itching&sym3=none&sym4=none&sym5=none => [Without Disease] <br/><br/>
> Response : `{"Precaution_1":"bath twice","Precaution_2":"use detol or neem in bathing water","Precaution_3":"keep infected area dry","Precaution_4":"use clean cloths"}`
 
<br/>

> [!NOTE]  
> Passing "none" is allowed also, provied we have to pass **all** **five** symptoms.

<br/>

Dataset used — https://www.kaggle.com/datasets/itachi9604/disease-symptom-description-dataset