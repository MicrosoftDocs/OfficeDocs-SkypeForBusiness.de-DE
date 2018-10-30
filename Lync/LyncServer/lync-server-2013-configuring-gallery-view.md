---
title: Konfigurieren der Katalogansicht
TOCTitle: Konfigurieren der Katalogansicht
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204871(v=OCS.15)
ms:contentKeyID: 49293915
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Katalogansicht

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Videokonferenzen in der Galerieansicht werden in Lync Server 2013 in der Konferenzrichtlinie konfiguriert. Die Galerieansicht ist standardmäßig aktiviert. Wenn Sie nicht möchten, dass die Galerieansicht verwendet wird, oder wenn diese Ansicht nur von bestimmten Benutzern verwendet werden soll, müssen Sie diese Funktion in der Konferenzrichtlinie deaktivieren.

Wenn das Video eines Konferenzteilnehmers nicht verfügbar ist, kann die Verwendung der Galerieansicht für den Benutzer durch das Bereitstellen hochauflösender Fotos verbessert werden. Dies ist eine neue Funktion in Lync Server 2013. Hochauflösende Fotos sind eine Alternative zu den kleineren Kontaktfotos mit begrenzter Auflösung, die in Active Directory-Domänendienste gespeichert werden. Hochauflösende Fotos werden im Exchange 2013-Postfach des Benutzers gespeichert. Aus diesem Grund ist die Integration von Lync Server 2013 in Exchange 2013 erforderlich. Nähere Informationen finden Sie im NextHop-Blog-Artikel "Integrating Exchange 2013 and Lync Server 2013" unter [http://go.microsoft.com/fwlink/?linkid=260987\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=260987%26clcid=0x407).


> [!NOTE]
> Die Inhalte der Blogs und die zugehörige URL können ohne vorherige Ankündigung geändert werden.



Sie können die Parameter der Galerieansicht mit Systemsteuerung für Lync Server 2013 oder mit einem der folgenden Cmdlets anzeigen oder bearbeiten:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Konfigurieren der Galerieansicht mit den folgenden Konferenzrichtlinieneinstellungen:

  - **AllowMultiview**   Dieser Parameter legt fest, ob ein Benutzer Videokonferenzen in der Galerieansicht organisieren kann. Die Festlegung des Parameters gilt für geplante Besprechungen ebenso wie für Ad-hoc-Besprechungen, die vom Benutzer erstellt werden.
    
    Beispiele:
    
      - Der Parameter ist für Benutzer A, der in einem Lync Server 2013-Pool verwaltet wird, auf "True" festgelegt. Bei Besprechungen, die von diesem Benutzer organisiert werden, können die Teilnehmer mehreren Videostreams beitreten bzw. diese empfangen.
    
      - Für Benutzer B, der in einem Lync Server 2013-Pool verwaltet wird, ist der Parameter auf "False" festgelegt. Besprechungen, die von diesem Benutzer organisiert werden, verfügen analog zur Videokonferenzfunktion von Lync Server 2010 nur über einen einzelnen Videostream.
    
    Dieser Parameter legt fest, welche Benutzer Besprechungen mit mehreren Videostreams organisieren können. Teilnehmer von Besprechungen, bei denen mehrere Videostreams zulässig sind, können diese empfangen, wenn sie dazu berechtigt sind (siehe Beschreibung für den EnableMultiviewJoin-Parameter). Andernfalls ist dies nicht möglich.

  - **EnableMultiviewJoin**   Dieser Parameter legt fest, ob Teilnehmer von Besprechungen, die dies zulassen, Videokonferenzen in der Galerieansicht nutzen können. Der Parameter wirkt sich auf alle Besprechungen aus, an denen ein Benutzer teilnimmt.
    
    Beispiele:
    
      - Der Parameter ist für Benutzer C auf "True" festgelegt. Benutzer C kann mehrere Videostreams empfangen, wenn er an einer Besprechung teilnimmt, die von Benutzer A organisiert oder gestartet wurde. Wenn Benutzer C an einer Besprechung teilnimmt, die von Benutzer B organisiert oder gestartet wurde, empfängt er analog zur Videokonferenzfunktion von Lync Server 2010 einen einzelnen Videostream.
    
      - Für Benutzer D ist der Parameter auf "False" festgelegt. Wenn Benutzer D an einer Besprechung teilnimmt, die von Benutzer A oder B organisiert wurde, empfängt er analog zur Videokonferenzfunktion von Lync Server 2010 einen einzelnen Videostream.

Im folgenden Verfahren wird gezeigt, wie Videokonferenzen in der Galerieansicht mit Lync Server-Verwaltungsshell aktiviert werden können.

## So bearbeiten Sie die Konferenzrichtlinie für Videokonferenzen in der Galerieansicht

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet über die Befehlszeile aus, um die Konferenzrichtlinie zu bearbeiten:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true

