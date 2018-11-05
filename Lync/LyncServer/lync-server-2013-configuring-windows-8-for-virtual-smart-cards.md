---
title: Konfigurieren von Windows 8 für virtuelle Smartcards
TOCTitle: Konfigurieren von Windows 8 für virtuelle Smartcards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn308564(v=OCS.15)
ms:contentKeyID: 56269267
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Windows 8 für virtuelle Smartcards

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Ein zu berücksichtigender Faktor, wenn zweistufige Authentifizierung und Smartcardtechnologie bereitgestellt werden, sind die Kosten der Implementierung. Windows 8 stellt eine Reihe neuer Sicherheitsfunktionen bereit, und eines der interessantesten neuen Features ist die Unterstützung von virtuellen Smartcards.

Bei Computern, die mit einem TPM-Chip (Trusted Platform Module) ausgerüstet sind, der die Spezifikationen von Version 1.2 erfüllt, können Organisationen nun die Vorteile einer Smartcardanmeldung nutzen, ohne in zusätzliche Hardware investieren zu müssen. Weitere Informationen hierzu finden Sie unter "Using Virtual Smart Cards with Windows 8" unter [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).

## So konfigurieren Sie Windows 8 für virtuelle Smartcards

1.  Melden Sie sich beim Windows 8-Computer mit den Anmeldeinformationen eines für Lync aktivierten Benutzers an.

2.  Bewegen Sie den Cursor auf der Windows 8-Startseite in die untere rechte Ecke des Bildschirms.

3.  Wählen Sie die Option **Suchen** aus, und suchen Sie dann nach **Eingabeaufforderung**.

4.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie dann **Als Administrator ausführen** aus.

5.  Öffnen Sie die TPM-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:
    
        Tpm.msc

6.  Vergewissern Sie sich in der TPM-Verwaltungskonsole, dass die TPM-Spezifikationsversion mindestens 1.2 ist.
    

    > [!NOTE]
    > Wird ein Dialogfeld angezeigt, in dem gemeldet wird, dass kein kompatibles Trusted Platform Module (TPM) gefunden wurde, sollten Sie sich vergewissern, dass der Computer ein kompatibles TPM hat und dass dieses im System-BIOS aktiviert ist.



7.  Schließen Sie die TPM-Verwaltungskonsole.

8.  Erstellen Sie über die Eingabeaufforderung eine neue virtuelle Smartcard, indem Sie folgenden Befehl ausführen:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    

    > [!NOTE]
    > Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert bereitstellen möchten, verwenden Sie "/pin prompt" anstelle von "/pin default".



9.  Öffnen Sie über die Eingabeaufforderung die Computerverwaltungskonsole, indem Sie den folgenden Befehl ausführen:
    
        CompMgmt.msc

10. Wählen Sie in der Computerverwaltungskonsole den Eintrag **Geräte-Manager** aus.

11. Erweitern Sie **Smartcard-Leser**.

12. Vergewissern Sie sich, dass der neue virtuelle Smartcardleser erfolgreich erstellt wurde.

