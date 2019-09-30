# Documentação para gerar uma nova fatura

Boleto

URL: https://api.botbr.app/novafatura


		
	Formato JSON POST
	{
		"modo": "modorequisicao", /* Produção ou Teste */ (obrigatório)
		"tokenid": "SEU TOKEN ID", (obrigatório)
		"authid": "SEU AUTH ID", (obrigatório)
		"metodo": "metodopagamento", /* boleto, credito ou debito */ (obrigatório) 

		"pagador":
		{
			"nome": "NOME PAGADOR",                    (obrigatório para boleto)
			"cpfcnpj": "CPFCNPJ PAGADOR",              (obrigatório para boleto)
			"cepPagador": "CEP PAGADOR",               (obrigatório para boleto)
			"enderecoPagador": "END PAGADOR",          (obrigatório para boleto)
			"numeroPagador": "NUMERO END PAGADOR",     (obrigatório para boleto)
			"bairroPagador": "BAIRRO PAGADOR",         (obrigatório para boleto)
			"cidadePagador": "CIDADE PAGADOR",         (obrigatório para boleto)
			"estadoPagador": "SIGLA ESTADO PAGADOR",   (obrigatório para boleto)

			"valorPorParcelaCobranca": VALOR DA PARCELA, /* Valores em Centavos */ (obrigatório)
			"parcelas": 1, (parcela em formato inteiro) (obrigatório)

			/* Fatura Boleto */
			"boleto":
			{
			    "vencimento" => "30/09/2019" /* Formato data: dd/mm/yyyy */ (obrigatório)
			}
		}
	}

