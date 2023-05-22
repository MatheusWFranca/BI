let
    DataMinima = List.Min(BaseVendas[Data da Venda]),
    DataMaxima = List.Max(BaseVendas[Data da Venda]),
    QtdDias = Duration.Days(DataMaxima - DataMinima) + 1,
    Calendario = List.Dates(DataMinima, QtdDias, #duration(1, 0, 0, 0))
in
    Calendario