---
title: 'Lync Server 2013: Definieren von optionalen Director-Topologien in einer Topologie'
TOCTitle: Definieren von optionalen Director-Topologien in einer Topologie
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398717(v=OCS.15)
ms:contentKeyID: 49294712
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren von optionalen Director-Topologien in einer Topologie für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Lync Server 2013-Directors können als Einzelinstanzserver bereitgestellt oder zur Verbesserung von Verfügbarkeit und Kapazität als Lastenausgleichspool mit mehreren Directors installiert werden. Sowohl Hardwarelastenausgleich als auch DNS-Lastenausgleich (Domain Name System) werden unterstützt. In diesem Thema wird erläutert, wie Sie den DNS-Lastenausgleich für Director-Pools konfigurieren.

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen **RTCUniversalServerAdmins** und **Domänen-Admins** angemeldet sein. Außerdem können Sie die erforderlichen Berechtigungen für das Hinzufügen von Serverrollen delegieren. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Bereitstellungsdokumentation für Standard Edition-Server oder Enterprise Edition-Server. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe **RTCUniversalServerAdmins** sein.

In diesem Thema wird beschrieben, welche Schritte erforderlich sind, um die Topologien für die beiden Director zu definieren und zu veröffentlichen:

  - So definieren Sie den Director (Einzelinstanz)

  - So definieren Sie den Director (Pool mit mehreren Directors)

## So definieren Sie den Director (Einzelinstanz)

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Klicken Sie auf der Startseite auf **Topologie aus einer vorhandenen Bereitstellung herunterladen** .

3.  Geben Sie im Dialogfeld **Topologie speichern unter** den Namen und den Speicherort für die lokale Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern** .

4.  Erweitern Sie den Standort, an dem der Director hinzugefügt werden soll, klicken Sie mit der rechten Maustaste auf **Director-Pools** und anschließend auf **Neuer Director-Pool** .

5.  Führen Sie im Dialogfeld **FQDN für Director-Pool definieren** die folgenden Schritte aus:
    
      - Geben Sie in **Pool-FQDN** den FQDN für den Director-Pool ein.
    
      - Klicken Sie auf **Pool mit einem Computer** und dann auf **Weiter** .

6.  Führen Sie im Dialogfeld **Dateifreigabe definieren** einen der folgenden Schritte aus:
    
    1.  Zum Verwenden einer vorhandenen Dateifreigabe klicken Sie auf **Zuvor definierte Dateifreigabe verwenden** , wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie auf **Weiter** .
    
    2.  Zum Erstellen einer neuen Dateifreigabe klicken Sie auf **Neue Dateifreigabe definieren** , geben Sie in **Dateiserver-FQDN** den FQDN für das Verzeichnis der Dateifreigabe ein, geben Sie in **Dateifreigabe** den Namen der Freigabe ein, und klicken Sie anschließend auf **Weiter** .
    

    > [!IMPORTANT]
    > Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor der Veröffentlichung der Topologie vorhanden sein oder erstellt werden.<BR>Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, Sie können dem Director also die Dateifreigabe jedes Pools in der Organisation zuweisen.



7.  Geben Sie im Dialogfeld **Webdienste-URL angeben** in **Externe Basis-URL** den FQDN für die Directors an, und klicken Sie anschließend auf **Fertig stellen** .
    

    > [!IMPORTANT]
    > Der Name muss von Internet-DNS-Servern aufgelöst werden können und auf die öffentliche IP-Adresse des Reverseproxys verweisen, der an diese URL gesendete HTTP/HTTPS-Anforderungen überwacht und diese an das virtuelle Verzeichnis der externen Webdienste auf diesem Director weiterleitet.

    

    > [!WARNING]
    > Wenn Sie mehr als einen Front-End-Pool oder Front-End-Server haben, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise <STRONG>pool01.contoso.com</STRONG> als FQDN für externe Webdienste eines Front-End-Servers definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen weiteren Front-End-Pool oder Front-End-Server verwenden. Wenn Sie außerdem Directors bereitstellen, darf der FQDN für externe Webdienste, den Sie für einen beliebigen Director oder Directorpool definieren, weder für andere Director oder Directorpools noch für andere Front-End-Pools oder Front-End-Server verwendet werden. Wenn Sie die internen Webdienste mit einem eigenen FQDN außer Kraft setzen, darf kein FQDN mit irgendeinem anderen Front-End-Pool, Director oder Directorpool übereinstimmen.



8.  Veröffentlichen Sie die Topologie.

## So definieren Sie den Director (Pool mit mehreren Directors)

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Klicken Sie auf der Startseite auf **Topologie aus einer vorhandenen Bereitstellung herunterladen** .

3.  Geben Sie im Dialogfeld **Topologie speichern unter** den Namen und den Speicherort für die lokale Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern** .

4.  Erweitern Sie den Standort, an dem der Director hinzugefügt werden soll, klicken Sie mit der rechten Maustaste auf **Director-Pools** und anschließend auf **Neuer Director-Pool** .

5.  Führen Sie im Dialogfeld **FQDN für Director-Pool definieren** die folgenden Schritte aus:
    
      - Geben Sie in **Pool-FQDN** den FQDN für den Director-Pool ein.
    
      - Klicken Sie auf **Pool mit mehreren Computern** und dann auf **Weiter** .

6.  Führen Sie im Dialogfeld **Computer in diesem Pool definieren** die folgenden Schritte aus:
    
      - Geben Sie den Computer-FQDN des ersten Mitglieds im Pool an, und klicken Sie anschließend auf **Hinzufügen** .
    
      - Wiederholen Sie diesen Schritt für jeden Computer, den Sie hinzufügen möchten, und klicken Sie zum Schluss auf **Weiter** .

7.  Führen Sie im Dialogfeld **Dateifreigabe definieren** einen der folgenden Schritte aus:
    
      - Zum Verwenden einer vorhandenen Dateifreigabe klicken Sie auf **Zuvor definierte Dateifreigabe verwenden** , wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie auf **Weiter** .
    
      - Zum Erstellen einer neuen Dateifreigabe klicken Sie auf **Neue Dateifreigabe definieren** , geben Sie in **Dateiserver-FQDN** den FQDN für das Verzeichnis der Dateifreigabe ein, geben Sie in **Dateifreigabe** den Namen der Freigabe ein, und klicken Sie anschließend auf **Weiter** .
    

    > [!IMPORTANT]
    > Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor der Veröffentlichung der Topologie vorhanden sein oder erstellt werden.<BR>Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, Sie können dem Director also die Dateifreigabe jedes Pools in der Organisation zuweisen.



8.  Geben Sie im Dialogfeld **Webdienste-URL angeben** in **Externe Basis-URL** den FQDN für die Directors an, und klicken Sie anschließend auf **Fertig stellen** .
    

    > [!IMPORTANT]
    > Der Name muss von Internet-DNS-Servern aufgelöst werden können und auf die öffentliche IP-Adresse des Reverseproxys verweisen, der an diese URL gesendete HTTP-/HTTPS-Anforderungen überwacht und diese an das virtuelle Verzeichnis der externen Webdienste in diesem Director-Pool weiterleitet.

    

    > [!WARNING]
    > Wenn Sie mehr als einen Front-End-Pool oder Front-End-Server haben, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise <STRONG>pool01.contoso.com</STRONG> als FQDN für externe Webdienste eines Front-End-Servers definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen weiteren Front-End-Pool oder Front-End-Server verwenden. Wenn Sie außerdem Directors bereitstellen, darf der FQDN für externe Webdienste, den Sie für einen beliebigen Director oder Directorpool definieren, weder für andere Director oder Directorpools noch für andere Front-End-Pools oder Front-End-Server verwendet werden. Wenn Sie die internen Webdienste mit einem eigenen FQDN außer Kraft setzen, darf kein FQDN mit irgendeinem anderen Front-End-Pool, Director oder Directorpool übereinstimmen.



9.  Veröffentlichen Sie die Topologie.

