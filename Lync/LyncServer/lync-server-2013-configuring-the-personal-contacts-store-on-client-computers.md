---
title: Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern
TOCTitle: Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49890997
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bei der Integration von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013 wird empfohlen, den persönlichen Kontaktspeicher auf allen Clientcomputern zu konfigurieren, auf denen Microsoft Lync 2010 ausgeführt wird. Insbesondere sollten Sie Lync für die Verwendung von Exchange als persönlichen Kontaktspeicher konfigurieren und gleichzeitig sicherstellen, dass diese Festlegung von den Benutzern nicht außer Kraft gesetzt werden kann. Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.

Beachten Sie, dass dies auf Computern, auf denen Lync 2013 ausgeführt wird, nicht erforderlich ist.

Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:

1.  Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl **regedit** ein, und drücken Sie die EINGABETASTE.

3.  Erweitern Sie im Registrierungs-Editor **HKEY\_LOCAL\_MACHINE**, dann **Software**, dann **Policies**, dann **Microsoft** und dann **Communicator**.

4.  Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf den Wert **DWORD-Wert (32-Bit)**.

5.  Geben Sie nach dem Erstellen des neuen Werts **PersonalContactStoreOverride** ein, und drücken Sie die EINGABETASTE, um den Wert umzubenennen.

6.  Stellen Sie sicher, dass der Wert von **PersonalContactStoreOverride** 0 ist, und schließen Sie dann den Registrierungs-Editor.

Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Ausführliche Informationen dazu finden Sie in der Doumentation zu Gruppenrichtlinien unter [http://go.microsoft.com/fwlink/?linkid=268543\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268543%26clcid=0x407).

