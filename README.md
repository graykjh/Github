1. 예측 모델 학습기의 소스코드 작성

        # 데이터 로드 - 압축 풀기 이후 진행사항
        f = open('Criteo_Conversion_Search/CriteoSearchData', mode = 'r', encoding='UTF-8')

        for line in f:
            tmp_array = line.strip().split(" ")
            while tmp_array.count(""):
                tmp_array.remove("")

            # \t 구분자로 Line 분할

            a=tmp_array[0].split("\t")
            result.append(list(a))

        df=pd.DataFrame(result)


