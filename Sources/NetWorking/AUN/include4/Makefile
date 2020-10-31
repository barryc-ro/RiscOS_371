# Makefile for include

# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date          Name         Description
# ----          ----         -----------
# 07-Feb-96     KJB          Created.

LIBDIR = <Lib$Dir>

#
# Generic options:
#
MKDIR   = cdir
WIPE    = -wipe
WFLAGS  = ~c~v

#
# Program specific options:
#
COMPONENT = include

HDRS = \
  arpa.h.ftp \
  arpa.h.inet \
  arpa.h.nameser \
  arpa.h.telnet \
  arpa.h.tftp \
  h.delay \
  h.errno \
  h.int_hndlr \
  h.ioc \
  h.netdb \
  h.pwd \
  h.riscos \
  h.sgtty \
  h.svcdebug \
  h.utmp \
  h.xcb \
  net.h.if \
  net.h.if_arp \
  net.h.netisr \
  net.h.raw_cb \
  net.h.route \
  netinet.h.icmp_var \
  netinet.h.if_ether \
  netinet.h.in \
  netinet.h.in_pcb \
  netinet.h.in_systm \
  netinet.h.in_var \
  netinet.h.ip \
  netinet.h.ip_icmp \
  netinet.h.ip_var \
  netinet.h.tcp \
  netinet.h.tcpip \
  netinet.h.tcp_debug \
  netinet.h.tcp_fsm \
  netinet.h.tcp_seq \
  netinet.h.tcp_timer \
  netinet.h.tcp_var \
  netinet.h.udp \
  netinet.h.udp_var \
  netns.h.ns \
  netns.h.ns_if \
  protocols.h.routed \
  rpc.h.auth \
  rpc.h.auth_unix \
  rpc.h.clnt \
  rpc.h.netdb \
  rpc.h.pmap_clnt \
  rpc.h.pmap_prot \
  rpc.h.pmap_rmt \
  rpc.h.rpc \
  rpc.h.rpc_msg \
  rpc.h.svc \
  rpc.h.svc_auth \
  rpc.h.types \
  rpc.h.xdr \
  rpcsvc.h.bootparam \
  sys.arm.h.fp \
  sys.h.acct \
  sys.h.buf \
  sys.h.callout \
  sys.h.clist \
  sys.h.conf \
  sys.h.dcistructs \
  sys.h.dir \
  sys.h.domain \
  sys.h.errno \
  sys.h.fcntl \
  sys.h.file \
  sys.h.ioctl \
  sys.h.ipc \
  sys.h.mbuf \
  sys.h.mount \
  sys.h.namei \
  sys.h.param \
  sys.h.proc \
  sys.h.protosw \
  sys.h.resource \
  sys.h.sem \
  sys.h.signal \
  sys.h.socket \
  sys.h.socketvar \
  sys.h.stat \
  sys.h.syscall \
  sys.h.syslog \
  sys.h.systm \
  sys.h.time \
  sys.h.timeb \
  sys.h.times \
  sys.h.tty \
  sys.h.ttychars \
  sys.h.ttydev \
  sys.h.types \
  sys.h.uio \
  sys.h.un \
  sys.h.unpcb \
  sys.h.user \
  sys.h.wait
  
FILES = ${HDRS}

all: $(FILES)

release: ${FILES}
   Copy arpa       TCPIPLibs4:arpa            ~CFLNR~V
   Copy h          TCPIPLibs4:h               ~CFLNR~V
   Copy machine    TCPIPLibs4:machine         ~CFLNR~V
   Copy net        TCPIPLibs4:net             ~CFLNR~V
   Copy netinet    TCPIPLibs4:netinet         ~CFLNR~V
   Copy netns      TCPIPLibs4:netns           ~CFLNR~V
   Copy netiso     TCPIPLibs4:netiso          ~CFLNR~V
   Copy protocols  TCPIPLibs4:protocols       ~CFLNR~V
   Copy rpc        TCPIPLibs4:rpc             ~CFLNR~V
   Copy rpcsvc     TCPIPLibs4:rpcsvc          ~CFLNR~V
   Copy sys        TCPIPLibs4:sys             ~CFLNR~V

#------------------------------------------------------------------------
# RISC OS Build targets:
#

export: export_${PHASE}

clean:
        @echo ${COMPONENT}: no cleaning required

#export_hdrs:
#        @echo ${COMPONENT}: export complete (hdrs)

export_libs: ${HDRS} dirs
        Copy arpa       TCPIPLibs4:arpa            ~CFLNR~V
        Copy h          TCPIPLibs4:h               ~CFLNR~V
        Copy machine    TCPIPLibs4:machine         ~CFLNR~V
        Copy net        TCPIPLibs4:net             ~CFLNR~V
        Copy netinet    TCPIPLibs4:netinet         ~CFLNR~V
        Copy netns      TCPIPLibs4:netns           ~CFLNR~V
        Copy netiso     TCPIPLibs4:netiso          ~CFLNR~V
        Copy protocols  TCPIPLibs4:protocols       ~CFLNR~V
        Copy rpc        TCPIPLibs4:rpc             ~CFLNR~V
        Copy rpcsvc     TCPIPLibs4:rpcsvc          ~CFLNR~V
        Copy sys        TCPIPLibs4:sys             ~CFLNR~V
        @echo ${COMPONENT}: export complete (libs)

dirs:
        ${MKDIR} ${LIBDIR}
        ${MKDIR} ${LIBDIR}.TCPIPLibs

# End of RISC OS Build targets
#------------------------------------------------------------------------

