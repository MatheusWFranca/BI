let
    DataMin = List.Min(BaseVendasCompleta[Data da Venda]),
    DataMax = List.Max(BaseVendasCompleta[Data da Venda]),
    QtdDias = Duration.Days(DataMax - DataMin) + 1,
    Personalizar1 = List.Dates(DataMin, QtdDias, #duration(1, 0, 0, 0)),
    #"Convertido para Tabela" = Table.FromList(Personalizar1, Splitter.SplitByNothing(), null, null, ExtraValues.Error),
    #"Colunas Renomeadas" = Table.RenameColumns(#"Convertido para Tabela",{{"Column1", "Data"}}),
    #"Tipo Alterado" = Table.TransformColumnTypes(#"Colunas Renomeadas",{{"Data", type date}})
in
    #"Tipo Alterado"