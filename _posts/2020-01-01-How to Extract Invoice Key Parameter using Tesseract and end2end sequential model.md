# How to Extract Invoice Key Parameter using Tesseract and end2end sequential model

> AIESI, Abstract Information Extraction from Scanned Invoice

[![Shreeshiv Patel](https://miro.medium.com/fit/c/56/56/1*RC57DE8oDQ40CsKg0PCjpg.jpeg)](chrome-extension://cjedbglnccaioiolemnfhjncicchinao/?source=post_page-----13cf2ffa9414--------------------------------)

![Image for post](https://miro.medium.com/max/50/1*pcRuk2EkpOZp4kk9W1V8Zw.jpeg?q=20)

![Image for post](https://miro.medium.com/max/1248/1*pcRuk2EkpOZp4kk9W1V8Zw.jpeg)

Key Invoice Parameter are highlighted with different colours. Source: SRPIE dataset for invoices.

What is AIESI?
--------------

Abstract Information Extrction from Scanned Invoice (AIESI) is an architecture to extract key information like, company name, invoice number, address, Tax amount, total amount, date, and etc. Simple OCR can only detect text from invoices. Task of AIESI is not only detect the text but we have to extract some useful key information from invoices.

**What are advantage of AIESI system?**
---------------------------------------

1\. AIESI helps to streamline data from scanned documents.

2\. For some application and system where we need to extract key information and store that into database AIESI is helpful.

3\. For getting complete insight of scanned documents, AIESI help to streamline data from scanned documents. This data can be used for fast indexing, archiving database and analytics.

4\. With recent advancement in deep learning, accuracy and processing time of AIESI improved significantly.

5\. For industries, like banking, medical, insurance, this system is very helpful.

What is pipeline?
-----------------

1\. Detect bouding box in invoices

2\. Extract text from bouding box

3\. Extract key information from extracted text from invoice(ETFI)

What is Tesseract?
------------------

Tesseact is OCR engine. Initially started as research project in HP, later in 2005 it becomes open source. Now tesseract is maintained by Google and it is open-source. More information can be find on its official paper, [https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/33418.pdf](http://tesseract%20ocr%20paper/)

For bounding box detectiong and extrcting text from scanned document, we are using tesseract engine. Many API and framwork available for this task. Google Mobile vision API, Amazon Textract, and etc. We can also use our own model for detecting bouding box and extract text enclosed in bouding box. CTPN can be used for detecting bouding box in scanned documents. Various architecture are also available for text detection in bounding box. Most methods combine CNN and RNN for extracting text from bounding box. CNN find visual features from document and RNN extract sequential features, to cop both we can detect text from bounding box.

For this post, I am using tesseract for **pipeline part 1 and 2**.

Complete pipelone Github repo can be find it here

How to run complete pipeline

1.  Fork complete project from above link,
2.  Download pre-trained model, model.pth file
3.  Run it.

If you can alternatively run it on Google Colab, just run Jupiter file _\[available at repo\]. Change path of output json file and input image file._

**If you like this post, HIT clap! Thanks for reading. Hope you like it. Cheers!** 😊.

Meanwhile I am working on a product, I call **Expense. AI** . It is a platform to store all invoices and bills at one location. We often lost invoices or cannot find when we need it. Using expense.AI we can store all invoices at one location. Download our FREE application on Google play store. Thanking you.


[Source](https://shreeshivpatel.medium.com/how-to-extract-invoice-key-parameter-using-tesseract-and-end2end-sequential-model-13cf2ffa9414)