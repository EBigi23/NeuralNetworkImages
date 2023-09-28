(50000, 32, 32, 3)
(50000, 32, 32, 3)
Model: "UNet"
__________________________________________________________________________________________________
 Layer (type)                   Output Shape         Param #     Connected to                     
==================================================================================================
 input_1 (InputLayer)           [(None, 32, 32, 3)]  0           []                               
                                                                                                  
 conv2d (Conv2D)                (None, 32, 32, 16)   448         ['input_1[0][0]']                
                                                                                                  
 conv2d_1 (Conv2D)              (None, 32, 32, 16)   2320        ['conv2d[0][0]']                 
                                                                                                  
 max_pooling2d (MaxPooling2D)   (None, 16, 16, 16)   0           ['conv2d_1[0][0]']               
                                                                                                  
 conv2d_2 (Conv2D)              (None, 16, 16, 32)   4640        ['max_pooling2d[0][0]']          
                                                                                                  
 conv2d_3 (Conv2D)              (None, 16, 16, 32)   9248        ['conv2d_2[0][0]']               
                                                                                                  
 max_pooling2d_1 (MaxPooling2D)  (None, 8, 8, 32)    0           ['conv2d_3[0][0]']               
                                                                                                  
 conv2d_4 (Conv2D)              (None, 8, 8, 64)     18496       ['max_pooling2d_1[0][0]']        
                                                                                                  
 conv2d_5 (Conv2D)              (None, 8, 8, 64)     36928       ['conv2d_4[0][0]']               
                                                                                                  
 max_pooling2d_2 (MaxPooling2D)  (None, 4, 4, 64)    0           ['conv2d_5[0][0]']               
                                                                                                  
 conv2d_6 (Conv2D)              (None, 4, 4, 64)     36928       ['max_pooling2d_2[0][0]']        
                                                                                                  
 conv2d_7 (Conv2D)              (None, 4, 4, 64)     36928       ['conv2d_6[0][0]']               
                                                                                                  
 dropout (Dropout)              (None, 4, 4, 64)     0           ['conv2d_7[0][0]']               
                                                                                                  
 max_pooling2d_3 (MaxPooling2D)  (None, 2, 2, 64)    0           ['dropout[0][0]']                
                                                                                                  
 conv2d_8 (Conv2D)              (None, 2, 2, 64)     36928       ['max_pooling2d_3[0][0]']        
                                                                                                  
 conv2d_9 (Conv2D)              (None, 2, 2, 64)     36928       ['conv2d_8[0][0]']               
                                                                                                  
 dropout_1 (Dropout)            (None, 2, 2, 64)     0           ['conv2d_9[0][0]']               
                                                                                                  
 up_sampling2d (UpSampling2D)   (None, 4, 4, 64)     0           ['dropout_1[0][0]']              
                                                                                                  
 conv2d_10 (Conv2D)             (None, 4, 4, 64)     16448       ['up_sampling2d[0][0]']          
                                                                                                  
 concatenate (Concatenate)      (None, 4, 4, 128)    0           ['dropout[0][0]',                
                                                                  'conv2d_10[0][0]']              
                                                                                                  
 conv2d_11 (Conv2D)             (None, 4, 4, 64)     73792       ['concatenate[0][0]']            
                                                                                                  
 conv2d_12 (Conv2D)             (None, 4, 4, 64)     36928       ['conv2d_11[0][0]']              
                                                                                                  
 up_sampling2d_1 (UpSampling2D)  (None, 8, 8, 64)    0           ['conv2d_12[0][0]']              
                                                                                                  
 conv2d_13 (Conv2D)             (None, 8, 8, 32)     8224        ['up_sampling2d_1[0][0]']        
                                                                                                  
 concatenate_1 (Concatenate)    (None, 8, 8, 96)     0           ['conv2d_5[0][0]',               
                                                                  'conv2d_13[0][0]']              
                                                                                                  
 conv2d_14 (Conv2D)             (None, 8, 8, 32)     27680       ['concatenate_1[0][0]']          
                                                                                                  
 conv2d_15 (Conv2D)             (None, 8, 8, 32)     9248        ['conv2d_14[0][0]']              
                                                                                                  
 up_sampling2d_2 (UpSampling2D)  (None, 16, 16, 32)  0           ['conv2d_15[0][0]']              
                                                                                                  
 conv2d_16 (Conv2D)             (None, 16, 16, 16)   2064        ['up_sampling2d_2[0][0]']        
                                                                                                  
 concatenate_2 (Concatenate)    (None, 16, 16, 48)   0           ['conv2d_3[0][0]',               
                                                                  'conv2d_16[0][0]']              
                                                                                                  
 conv2d_17 (Conv2D)             (None, 16, 16, 16)   6928        ['concatenate_2[0][0]']          
                                                                                                  
 conv2d_18 (Conv2D)             (None, 16, 16, 16)   2320        ['conv2d_17[0][0]']              
                                                                                                  
 up_sampling2d_3 (UpSampling2D)  (None, 32, 32, 16)  0           ['conv2d_18[0][0]']              
                                                                                                  
 conv2d_19 (Conv2D)             (None, 32, 32, 8)    520         ['up_sampling2d_3[0][0]']        
                                                                                                  
 concatenate_3 (Concatenate)    (None, 32, 32, 24)   0           ['conv2d_1[0][0]',               
                                                                  'conv2d_19[0][0]']              
                                                                                                  
 conv2d_20 (Conv2D)             (None, 32, 32, 8)    1736        ['concatenate_3[0][0]']          
                                                                                                  
 conv2d_21 (Conv2D)             (None, 32, 32, 8)    584         ['conv2d_20[0][0]']              
                                                                                                  
 conv2d_22 (Conv2D)             (None, 32, 32, 3)    219         ['conv2d_21[0][0]']              
                                                                                                  
 conv2d_23 (Conv2D)             (None, 32, 32, 3)    12          ['conv2d_22[0][0]']              
                                                                                                  
==================================================================================================
Total params: 406,495
Trainable params: 406,495
Non-trainable params: 0
