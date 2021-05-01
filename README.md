# 1. 예측 모델 학습기의 소스코드 작성

        # 데이터 로드 - 압축 풀기 이후 진행사항
        f = open('Criteo_Conversion_Search/CriteoSearchData', mode = 'r', encoding='UTF-8')
        
        reusult = []

        for line in f:
            tmp_array = line.strip().split(" ")
            while tmp_array.count(""):
                tmp_array.remove("")

            # \t 구분자로 Line 분할

            a=tmp_array[0].split("\t")
            result.append(list(a))

        # 해당 List를 데이터 프레임으로 변경
        df=pd.DataFrame(result)
        
        # 로지스틱 회귀 모델링 진행 
        from sklearn.linear_model import LogisticRegression
        from sklearn.model_selection import train_test_split
        
        X=cav1.iloc[:,1:]
        y=cav1.iloc[:,1]
        
        X_train = X.loc[1:1000001,:]
        X_test = X.loc[1000001:1500000:]
        
        y_train = y.loc[1:1000001,:]
        y_test = y.loc[1000001:1500000:]
        
        model = LogisticRegression()
        model.fit(X_train, y_train)
        


