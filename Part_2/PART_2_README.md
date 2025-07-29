Я изучил работу (https://github.com/VladimirShtefan/Lesson_21_Abstract_methods) 
Я обнаружил следующие запахи:

1. Дублирование кода
В классах Shop и Store метод get_storage_name дублируют метод с таким же названием 
в классе BaseStorage. 
    Этот метод в классах Shop и Store можно удалить.

Другие улучшения, не относящиеся к плохим запахам:

1. В классе Request метод parse_data ловит ErrorBadRequest, 
но не возвращает None явно в случае ошибки. 
Откорректированный код:
    def parse_data(self) -> dict | None:
        try:
            storage, amount, product = self._get_data_for_order()
        except ErrorBadRequest as e:
            print(e.message)
            return None
        else:
            ...

2. 
