---
title: Konfigurieren von AD FS 2.0, sodass Clientauthentifizierung unterstützt wird
TOCTitle: Konfigurieren von AD FS 2.0, sodass Clientauthentifizierung unterstützt wird
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn308565(v=OCS.15)
ms:contentKeyID: 56269270
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von AD FS 2.0, sodass Clientauthentifizierung unterstützt wird

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 Authentifizierung über Smartcards unterstützen kann:

  - Formularbasierte Authentifizierung (FBA)

  - Transport Layer Security-Clientauthentifizierung

Wenn Sie formularbasierte Authentifizierung verwenden, können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mit der Kombination aus Benutzername und Kennwort oder mit Smartcard und PIN zu authentifizieren. Im vorliegenden Thema wird beschrieben, wie Transport Layer Security-Clientauthentifizierung mit AD FS 2.0 implementiert wird. Weitere Informationen zu den Authentifizierungstypen von AD FS 2.0 finden Sie unter "AD FS 2.0: How to Change the Local Authentication Type" unter [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).


**So konfigurieren Sie AD FS 2.0, sodass Clientauthentifizierung unterstützt wird**

1.  Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.

2.  Starten Sie Windows-Explorer.

3.  Navigieren Sie zu "C:\\inetpub\\adfs\\ls".

4.  Erstellen Sie eine Sicherungskopie von der vorhandenen Datei "web.config".

5.  Öffnen Sie die vorhandene Datei "web.config" mit Editor.

6.  Wählen Sie in der Menüleiste das Menü **Bearbeiten** aus, und wählen Sie dann **Suchen** aus.

7.  Suchen Sie nach **\<localAuthenticationTypes\>**.
    
    Es werden vier Authentifizierungstypen aufgelistet (je ein Typ pro Zeile).

8.  Verschieben Sie die Zeile, die den Authentifizierungstyp "TLSClient" enthält, an den Anfang der Liste im Abschnitt.

9.  Speichern Sie die Datei "web.config", und beenden Sie Editor.

10. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.

11. Starten Sie IIS neu, indem Sie folgenden Befehl ausführen:
    
        IISReset /Restart /NoForce

