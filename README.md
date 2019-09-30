# Documentação para gerar uma nova fatura

URL: https://api.botbr.app/novafatura

### Boleto (Formato JSON POST)
```	
{
  "modo": "modorequisicao",                          /* producao ou teste (obrigatório) */
  "tokenid": "SEU TOKEN ID",                         /* Gerado na plataforma APP BotBR (obrigatório) */
  "authid": "SEU AUTH ID",                           /* Gerado na plataforma APP BotBR (obrigatório) */
  "metodo": "metodopagamento",                       /* boleto, credito ou debito (obrigatório) */ 
	
  "descricaoPagamento": "Sua desc. do pag.",         /* (Não Obrigatório) Max: 100 carac. */

  "pagador":
  {
    "nome": "NOME PAGADOR",                          /* (obrigatório para boleto)   Max: 255 carac. */
    "cpfcnpj": "CPFCNPJ PAGADOR",                    /* (obrigatório para boleto)                   */
    "email": "Email do Pagador",                     /* (Não obrigatório)           Max: 255 carac. */
    "cepPagador": "CEP PAGADOR",                     /* (obrigatório para boleto)                   */
    "enderecoPagador": "END PAGADOR",                /* (obrigatório para boleto)   Max: 255 carac. */
    "numeroPagador": "NUMERO END PAGADOR",           /* (obrigatório para boleto)   Max: 15 carac.  */
    "bairroPagador": "BAIRRO PAGADOR",               /* (obrigatório para boleto)   Max: 100 carac. */
    "complementoPagador": "Ex. AP 32",               /* (Não obrigatório)           Max: 50 carac.  */
    "cidadePagador": "CIDADE PAGADOR",               /* (obrigatório para boleto)   Max: 50 carac.  */
    "estadoPagador": "SIGLA ESTADO PAGADOR",         /* (obrigatório para boleto)   Max: 02 carac.  */

    "valorPorParcelaCobranca": VALOR DA PARCELA,     /* Valores em Centavos (obrigatório)           */
    "parcelas": 1,                                   /* Boleto somente uma parcela (obrigatório)    */
    
    "boleto":
    {
      "vencimento": "01/01/2019",                    /* Formato data: dd/mm/yyyy (obrigatório)      */
      "fraseBoleto01": "Frase 01 do Boleto",         /* (Não obrigatório)   Max: 02 carac.          */
      "fraseBoleto02": "Frase 02 do Boleto",         /* (Não obrigatório)   Max: 02 carac.          */
      "fraseBoleto03": "Frase 03 do Boleto",         /* (Não obrigatório)   Max: 02 carac.          */
      "desconto": "porcentagem desconto",            /* (Não obrigatório) Formato inteiro 
      							Ex: 12,45% = 1245                           */
							
      "juros": "porcentagem juros"                   /* (Não obrigatório) Formato inteiro 
      							Cobrado somente se o boleto for pago após 
							o vencimento  
      							Ex: 12,45% = 1245                           */
							
      "multa": "porcentagem multa"                   /* (Não obrigatório) Formato inteiro 
      							Cobrado somente se o boleto for pago após 
							o vencimento  
      							Ex: 12,45% = 1245                           */
    }
  }
	
  "codReferencia": "Codigo de referência da sua loja",     /* Somente letras e números sem acentos 
    							      ou carac. esp. 				*/
}
```
