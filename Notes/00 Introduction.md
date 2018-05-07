###Machine Learning definition
- Arthur Samuel(1959). Machine Learning: Field of study that gives computers the ability to learn without being explicitly programmed.
- Tom Mitchell(1998). A computer program is said to learn from experience E(experience) with respect to some task T(task) and some performance measure P, if its performance on T, as measured by  P(probability), improves with experience E.

###Machine learning algorithms:

####Supervised learning
- Regression Problem
- Classification Problem

####Unsupervised learning
 - cluster 
   - Organize computing clusters
   - Social network analysis
   - Market segmentation
   - Astronomical data analysis
 - Cocktail party problem: `find structure in a chaotic environment`
 
   ```
    [W, s, v] = svd((repmat(sum(x.*x, 1), size(x, 1), 1).*x)*x’);
   ```
    
    Svd 奇异值分解(解线性方程)

####Reinforcement learning

####recommender systems

###Matrices and vectors
####definition
- $\mathbb{R}$ refers to the set of scalar real numbers.
- $\mathbb{R^n}$ refers to the set of n-dimemsional vectors of real numbers.

###Matlab
1. 更改Octave命令提示

    ```
    PS1(‘>> ’);
    ```

2. 打印结果

    ```
    disp(sprintf(‘2 decimals: %0.2f’, a));
    ```

3. 特殊矩阵
    
    ```
        ones(a, b);
        rand(a, b);
        randn(a, b);
        eye(a, b);
        magic(a);
        
    ```
    
4. 绘图

    ```
        hold on； %继续绘制
        ploy(x, y); %折线图
        hist(w, h); %条状图
        xlabel(‘’);
        ylabel(‘’);
        title(‘’);
        legend(‘sin’, ‘cos’); %标记曲线
        print -dpng ‘myPlot.png’; %图像存储为文件
        axis（[x_min x_max y_min y_max]）; %缩放
        clf； %清除图像
        imagesc(A) %将矩阵绘制为图像
    ```
    
5. 控制语句
    
    ```
        for i = 1:10
            v(i) = i^2;
        end;
        
        while i <= 5
            v(i) = 100;
            i = i + 1;
        end;
        
        if v(1) == 1,
            disp(‘value is one’);
        elseif v(1) == 2,
            disp(‘two’);
        end;
    ```
    
6. Max

    ```
        [value, index] = max()
        max(A, [], 1); %每列最大值
        max(A, [], 2); %每行最大值
   ``` 

7. 函数定义


    ```
        function [y1, y2] = squareAndCUbeThisNumber(x)
            y1 = x^2;
            y2 = x^3;
    ```
    
8. 其他命令

|  命令格式  |     用途   |
| :-------: | :-------: |
|pwd|打印当前路径|
|cd|更改路径|
|ls|列出当前路径的文件|
|load featuresX.dat|加载数据|
|load(‘featuresX.dat’)|加载数据|
|who|显示当前变量列表|
|whos|详细查看当前变量列表|
|clear|清空当前变量列表|
|save xxx.mat|将当前变量列表存储到文件|
|save xxx.mat -v name|将workspace中的变量[name]存储到文件|
|save xxx -ascii|以文本形式存储|
|addpath(‘’)|增加路径|
|search path()|搜索路径|
