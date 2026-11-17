# U3-SISTEMA-DE-VENTAS-MACROS-PROCEDIMIENTOS-Y-USES-
# FACILITADOR: DR.MEDINA.
# DOCUMENTACION DE LEON FERNANDEZ ALEXIS JAVIER 8-9HRS.

RETROALIMENTACION DEL PROYECTO U2 ...RECICLANDO LINEAS DE CODIGO IMPLEMENTANDO MACROS...
#Para estar en contexto la version anterior hemos puesto un archivo binario INV1 y seguridad implementada mediante proto/invoke ..ahora se ha optado por guardarlo en un archivo txt para facilitación de lectura 
mPrint texto	mov edx,OFFSET msg + call WriteString	13	ShowProduct (3), DoRegister (2), AskValidated, PrintUInt, PrintMoney, SelectProduct, ShowInventory, DoSell, ShowSummary, main	No
mPrintValue texto, valor, rutina	Mostrar una etiqueta y luego un número o dinero	6	ShowSummary (3), ShowProduct (2), DoSell	No
mRetOK	clc + ret (regresar "todo bien")	19	ReadField (3) y 16 procedimientos más, una vez cada uno	No
mRetError	stc + ret (regresar "error")	17	Los mismos 17 procedimientos	No
mJmpOutOfRange valor, min, max, destino	cmp/jb/cmp/ja para validar rangos	11	ParsePrice (3), ValidateCode (2), ParseUnsigned, ParseInRange, ValidateName, ValidateRecord, ReceiveStock, SellProduct	No
mAppendDigit digito, destino	Bloque de 7 líneas: número×10 + dígito, con revisión de desbordamiento	2	ParseUnsigned, ParsePrice	No
mZeroMem dir, bytes	rep stosb para llenar con ceros	2	DoRegister, ParseTextFile	No
mCopyMem dest, origen, bytes	rep movsb con su preparación de registros	2	RegisterCandidate, LoadCatalog	No
mAskWith mensaje, validador	Preparar EDX y EDI y llamar a AskValidated	3	DoRegister (2), AskCode	No
mAskNumber mensaje, min, max	mov edx/ebx/ebp + call AskUnsigned	5	main (2), DoRegister, AskProductQuantity, DoLoad	No
mReportCF textoOK, textoError	jc → mensaje de éxito o de error	4	DoRegister, DoReceive, SaveWithMessage, LoadWithMessage	Sí
mPutChar caracter	mov [edi],x + inc edi	5	FormatLine	No
mStoreHandle destino	Revisar INVALID_HANDLE_VALUE y guardar el manejador	2	LoadCatalog, SaveCatalog	No
mCloseHandle	mov eax,fileHandle + call CloseFile	4	LoadCatalog (2), SaveCatalog (2)	No
