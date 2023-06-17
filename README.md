# handwriting recognition
## CRNN Model
CRNN is composed of CNN & RNN, it has three layers:  
* Convolutional layers:  
A CNN model without fully-connected layers  
* Recurrent layers:  
It is a deep bi-directional LSTM, built for making prediction for each frame of the feature sequence  
* Transciption Layer:  
It is adopted to translate the per-frame predictions by the recurrent layers into a label sequence
```
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 input (InputLayer)          [(None, 256, 64, 1)]      0         
                                                                 
 conv1 (Conv2D)              (None, 256, 64, 32)       320       
                                                                 
 batch_normalization (BatchN  (None, 256, 64, 32)      128       
 ormalization)                                                   
                                                                 
 activation (Activation)     (None, 256, 64, 32)       0         
                                                                 
 max1 (MaxPooling2D)         (None, 128, 32, 32)       0         
                                                                 
 conv2 (Conv2D)              (None, 128, 32, 64)       18496     
                                                                 
 batch_normalization_1 (Batc  (None, 128, 32, 64)      256       
 hNormalization)                                                 
                                                                 
 activation_1 (Activation)   (None, 128, 32, 64)       0         
                                                                 
 max2 (MaxPooling2D)         (None, 64, 16, 64)        0         
                                                                 
 dropout (Dropout)           (None, 64, 16, 64)        0         
                                                                 
 conv3 (Conv2D)              (None, 64, 16, 128)       73856     
                                                                 
 batch_normalization_2 (Batc  (None, 64, 16, 128)      512       
 hNormalization)                                                 
                                                                 
 activation_2 (Activation)   (None, 64, 16, 128)       0         
                                                                 
 max3 (MaxPooling2D)         (None, 64, 8, 128)        0         
                                                                 
 dropout_1 (Dropout)         (None, 64, 8, 128)        0         
                                                                 
 reshape (Reshape)           (None, 64, 1024)          0         
                                                                 
 dense1 (Dense)              (None, 64, 64)            65600     
                                                                 
 lstm1 (Bidirectional)       (None, 64, 512)           657408    
                                                                 
 lstm2 (Bidirectional)       (None, 64, 512)           1574912   
                                                                 
 dense2 (Dense)              (None, 64, 30)            15390     
                                                                 
 softmax (Activation)        (None, 64, 30)            0         
                                                                 
=================================================================
Total params: 2,406,878
Trainable params: 2,406,430
Non-trainable params: 448
_________________________________________________________________
```

## CTC Loss
An algorithm used to train deep neural networks in handwriting recognition, it is a way to get around not knowing the alignment between the input and the output

## Recognition
Correct characters predicted : 85.15%  
Correct words predicted      : 70.73%  

![image](https://github.com/reeve8844/handwriting_recognition/assets/39294948/6a2e3219-204c-407c-95d8-99ef3895b3c2)

```
Identity: KEVIN                    	 Predict: KEVIN                   
Identity: CLOTAIRE                 	 Predict: CLOTITY                 
Identity: LENA                     	 Predict: LEMA                    
Identity: JULES                    	 Predict: JULES                   
Identity: CHERPIN                  	 Predict: CHERPIN                 
Identity: MARTIN                   	 Predict: MARTIN                  
Identity: VALENTINE                	 Predict: VALENTINE               
Identity: LORAS                    	 Predict: LORAS                   
Identity: THIBAULT                 	 Predict: THIBAULT                
Identity: AZABI                    	 Predict: AZAOA                   
Identity: GORTCHAKOFF              	 Predict: GORTHAKOT               
Identity: MAHENTHIRAN              	 Predict: MAHENTHIRAN             
Identity: FRANSOISSISEPH           	 Predict: FRANEOISSSIEP           
Identity: JEANNE                   	 Predict: JEANNE                  
Identity: DEBORAH                  	 Predict: DEBORAH                 
Identity: DROUCS                   	 Predict: BDROUES                 
Identity: JADE                     	 Predict: JOYC                    
Identity: CORNIL FRERROT           	 Predict: CORNIL FRERROT          
Identity: CLEMET                   	 Predict: CLEMENT                 
Identity: RELIS                    	 Predict: KMAELIS                 
Identity: NAMIZATA FATIM           	 Predict: MNAMIZATA FATIHE        
Identity: FOURNEL                  	 Predict: FOURNEL                 
Identity: DICINTIO-ILLESCA         	 Predict: DICINTIO-ILLESC         
Identity: BARDOT                   	 Predict: BARDOT                  
Identity: DUVAL                    	 Predict: DUVAL                   
Identity: ANTONY                   	 Predict: ANTONY                  
Identity: LISA                     	 Predict: LISA                    
Identity: CELIA                    	 Predict: CELIA                   
Identity: GRODZKI                  	 Predict: GRODZKI                 
Identity: HUGO                     	 Predict: HUGO                    
Identity: HUGO                     	 Predict: HUGO                    
Identity: ELOUEN                   	 Predict: ELOUEN                  
Identity: SCHOEMAECKER             	 Predict: SCHOMAEC                
Identity: HOARAU                   	 Predict: MHOARAU                 
Identity: STEENKERSTE              	 Predict: STEEKERSTE              
Identity: DI -FONZO                	 Predict: DI-FONZO                
Identity: BUIREY                   	 Predict: BUIREY                  
Identity: ROMAN                    	 Predict: ROMAN                   
Identity: MILLE                    	 Predict: MILLE                   
Identity: CAROLINE                 	 Predict: CAROLINE                
Identity: PAUL                     	 Predict: PAUL                    
Identity: BECHARA                  	 Predict: BELHARA                 
Identity: DIBOS                    	 Predict: DIBOS                   
Identity: JEAN COME                	 Predict: JEAN COME               
Identity: DRENIN                   	 Predict: DRENIN                  
Identity: CLOUIS                   	 Predict: CLOVIS                  
Identity: JORIS                    	 Predict: JORIS                   
Identity: NARDINI                  	 Predict: MIRDINI                 
Identity: CLAIRE                   	 Predict: CLAIRE                  
Identity: RAFFORT                  	 Predict: RAFFORT                 
```
