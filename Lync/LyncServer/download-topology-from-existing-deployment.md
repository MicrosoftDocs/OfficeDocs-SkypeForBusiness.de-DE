---
title: Herunterladen der Topologie aus einer vorhandenen Bereitstellung
TOCTitle: Herunterladen der Topologie aus einer vorhandenen Bereitstellung
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49890978
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Herunterladen der Topologie aus einer vorhandenen Bereitstellung

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Wenn Sie eine Lync Server 2013-Pool erstellen, verwenden Sie den zentralen Verwaltungsspeicher, der Lync Server 2010 zugeordnet ist. Beim erstmaligen Starten des Topologie-Generators und in nachfolgenden Bearbeitungssitzungen werden Sie zur Angabe des Speicherorts aufgefordert, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll. Da Sie bereits eine Lync Server 2010-Topologie definiert und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen. Der Topologie-Generator liest die Informationen aus der Datenbank und ruft die aktuelle Definition ab.

**So laden Sie eine Topologie aus einer vorhandenen Bereitstellung herunter**

1.  Öffnen Sie den Lync Server-Bereitstellungs-Assistenten.

2.  Klicken Sie auf der Seite **Lync Server 2013 - Bereitstellungs-Assistent** auf **Verwaltungstools installieren** .

3.  Starten des Topologie-Generators: Klicken Sie auf **Start** , zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013** , und klicken Sie anschließend auf **Lync Server-Topologie-Generator** .

4.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.
    
    ![Einstellungen des Bereitstellungs-Assistenten des Topologie-Generators](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Einstellungen des Bereitstellungs-Assistenten des Topologie-Generators")

5.  Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie als standardmäßigen TBXML-Dateityp.

6.  Erweitern Sie den Lync Server-Knoten (siehe Abbildung), um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.
    
    ![Topologie-Generator: allgemeine Eigenschaften der Serverrolle](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topologie-Generator: allgemeine Eigenschaften der Serverrolle")

