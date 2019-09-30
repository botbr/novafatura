# Documentação para gerar uma nova fatura

URL: https://api.botbr.app/novafatura

### Boleto (Formato JSON POST)
```	
{
  "modo": "modorequisicao",     /* producao ou teste (obrigatório) */
  "tokenid": "SEU TOKEN ID",    /* Gerado na plataforma APP BotBR (obrigatório) */
  "authid": "SEU AUTH ID",      /* Gerado na plataforma APP BotBR (obrigatório) */
  "metodo": "metodopagamento",  /* boleto, credito ou debito (obrigatório) */ 
	
  "descricaoPagamento": "Sua descricao do pagamento", /* (Não Obrigatório) Max: 100 carac. */

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
      "vencimento" => "01/01/2019"                 /* Formato data: dd/mm/yyyy (obrigatório)      */
    }
  }
	
  "codReferencia": "Codigo de referência da sua loja",     /* Somente letras e números sem acentos 
    							      ou carac. esp. 				*/
}
```
