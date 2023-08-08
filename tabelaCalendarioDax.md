dCalendario = 

var anoMin = YEAR(MIN(fVendas[Data da Venda]))
var anoMax = YEAR(MAX(fVendas[Data da Venda]))

RETURN CALENDAR(
    DATE(anoMin;01;01); 
    DATE(anoMax; 12;31)
)


