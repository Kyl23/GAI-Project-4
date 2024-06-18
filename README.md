# GAI-Project-4
參考來源：https://www.kaggle.com/code/sachin/ddpm-mnist

## 文件説明
### ddpm.ipynb
- 這是一個通過輸入噪聲由ddpm模型去噪的模型程式

### ddpm-with-dip.ipynb
- 這是一個通過輸入噪聲先由dip模型去噪后再由ddpm的模型再次去噪的程式

## 如何使用
### ddpm.ipynb
1. 將程式執行直到def train之後
2. 執行train(epochs)並輸入想訓練的epoch次數
3. 可以通過torch.save將模型保存
> 可以通過 ```generate_denoised_images_ddpm(model.eval(), NUM_DIFFUSION_STEPS, noise, noise_scheduler)``` 生成最終圖片

### ddpm-with-dip.ipynb
1. 將程式執行直到 `Train DIP` 的def train之後
2. 執行train(epochs)並輸入想訓練的epoch次數
3. 可以通過torch.save將模型保存
4. 將dip載入或直接接著原來的dip使用
5. 將程式執行直到 `Train DDPM + DIP` 的def train之後
6. 執行train(epochs)並輸入想訓練的epoch次數
7. 可以通過torch.save將模型保存
> 可以通過 ```generate_denoised_images_ddpm(dip.eval(), model.eval(), NUM_DIFFUSION_STEPS, noise, noise_scheduler)``` 生成最終圖片
> 
> 也可以只通過 ```dip(noise)```來生成dip之後的圖片
