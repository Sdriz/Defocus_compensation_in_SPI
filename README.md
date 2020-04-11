
===============================================================================
=                      Deep Learning based defocus compensation               =
=                             in Single pixel imaging                         =
===============================================================================
Author:  SRIZVI email:srizvi@bit.edu.cn
License: Academic free license V3 (afl-3.0), see License.txt
Version: 1.0 
URL:     https://github.com/Sdriz/Defocus_compensation_in_SPI









### Defocusing_in_SPI MODEL
Defocus compensation model
The h5. file can be downloaded to inspect the DCNN model with trained weights, parameters etc.

### Model summary 

model.summary()

### Load target affect by projector defocusing
target=io.loadmat('target.mat')

#### Ouput of Model after model load
   result_target = model.predict(target.reshape(1,96,96,1))







### Supplementary

#####Laoding target one by one 
#different targetscan be loaded from:
import h5py

def load_dataset(file_location,target):
    hf = h5py.File( file_location , 'r')
    fl = hf[target]
    new_array = np.array(fl)
    hf.close()
    return new_array

#Insert location
file_location = ''

#### Testing data
tar_container = ['target2',  'target2', 'target3','target4']

tar_dict = {}
for elm in Who:
####
    tar_load = 'repository/Original_images/' + iter
    tar_dict[iter] = load_dataset(file_location, tar_load)
   

