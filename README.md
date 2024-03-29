# 2019-Wim-Jongman-iUnit
Ibm i Unit Testing framework

## Install iUnit
https://github.com/i-unit/iunit

## Create the Unit to test
* CRTLIB IUNITS1
* CRTSRCPF IUNITS1/QRPGLESRC RCDLEN(112)
* ADDPFM FILE(IUNITS1/QRPGLESRC) MBR(MATH) SRCTYP(RPGLE) // Copy MATH.RPGLE
* ADDPFM FILE(IUNITS1/QRPGLESRC) MBR(MATHPR) SRCTYP(RPGLE) // Copy MATHPR.RPGLE
* CRTRPGMOD MODULE(IUNITS1/MATH) SRCFILE(IUNITS1/QRPGLESRC) SRCMBR(MATH) OPTION(*EVENTF) DBGVIEW(*SOURCE) REPLACE(*YES)
* CRTSRVPGM SRVPGM(IUNITS1/MATH) MODULE(IUNITS1/MATH) EXPORT(*ALL)

## Create the tests
* CRTSRCPF IUNITS1/QCLLESRC RCDLEN(112)
* CRTDUPOBJ OBJ(UTEMSG) FROMLIB(IUNIT) OBJTYPE(*MSGF) TOLIB(IUNITS1) 
* ADDPFM FILE(IUNITS1/QRPGLESRC) MBR(MINTEST) SRCTYP(CLLE) // Copy MINTEST.CLLE
* ADDPFM FILE(IUNITS1/QRPGLESRC) MBR(ADDTEST) SRCTYP(CLLE) // Copy ADDTST.CLLE
* ADDPFM FILE(IUNITS1/QRPGLESRC) MBR(DIVTEST) SRCTYP(CLLE) // Copy DIVTESTCLLE
* ADDPFM FILE(IUNITS1/QRPGLESRC) MBR(I_SETUP) SRCTYP(CLLE) // Copy I_SETUP.CLLE
* ADDPFM FILE(IUNITS1/QRPGLESRC) MBR(I_TEARDOWN) SRCTYP(CLLE) // Copy I_TEARDOWN.CLLE

* Compile all members with CRTBNDCL

## Run the Tests
* addlible iunit *last
* runall libc(iunits1)

## Code Coverage
https://www.ibm.com/support/knowledgecenter/SSAE4W_9.6.0/com.ibm.debug.pdt.codecoverage.i.doc/topics/tcc_sep.html






