# Documentação para gerar uma nova fatura

URL: https://api.botbr.app/novafatura

### Boleto (Formato JSON POST)
```	
{
	"modo": "modorequisicao",     /* Produção ou Teste (obrigatório) */
	"tokenid": "SEU TOKEN ID",    /* Gerado na plataforma APP BotBR (obrigatório) */
	"authid": "SEU AUTH ID",      /* Gerado na plataforma APP BotBR (obrigatório) */
	"metodo": "metodopagamento",  /* boleto, credito ou debito (obrigatório) */ 

	"pagador":
	{
		"nome": "NOME PAGADOR",                    /* (obrigatório para boleto) */
		"cpfcnpj": "CPFCNPJ PAGADOR",              /* (obrigatório para boleto) */
		"cepPagador": "CEP PAGADOR",               /* (obrigatório para boleto) */
		"enderecoPagador": "END PAGADOR",          /* (obrigatório para boleto) */
		"numeroPagador": "NUMERO END PAGADOR",     /* (obrigatório para boleto) */
		"bairroPagador": "BAIRRO PAGADOR",         /* (obrigatório para boleto) */
		"cidadePagador": "CIDADE PAGADOR",         /* (obrigatório para boleto) */
		"estadoPagador": "SIGLA ESTADO PAGADOR",   /* (obrigatório para boleto) */

		"valorPorParcelaCobranca": VALOR DA PARCELA, /* Valores em Centavos (obrigatório) */
		"parcelas": 1, (parcela em formato inteiro)  /* (obrigatório) */
	
		"boleto":
		{
		    "vencimento" => "01/01/2019" /* Formato data: dd/mm/yyyy (obrigatório) */
		}
	}
}
```
