dnl
dnl Software pw3270, desenvolvido com base nos códigos fontes do  C3270  e  X3270
dnl (Paul Mattes Paul.Mattes@usa.net), de emulação de terminal 3270 para acesso a
dnl aplicativos mainframe. Registro no INPI sob o nome G3270.
dnl
dnl Copyright (C) <2008> <Banco do Brasil S.A.>
dnl
dnl Este programa é software livre. Você pode redistribuí-lo e/ou modificá-lo sob
dnl os termos da GPL v.2 - Licença Pública Geral  GNU,  conforme  publicado  pela
dnl Free Software Foundation.
dnl
dnl Este programa é distribuído na expectativa de  ser  útil,  mas  SEM  QUALQUER
dnl GARANTIA; sem mesmo a garantia implícita de COMERCIALIZAÇÃO ou  de  ADEQUAÇÃO
dnl A QUALQUER PROPÓSITO EM PARTICULAR. Consulte a Licença Pública Geral GNU para
dnl obter mais detalhes.
dnl
dnl Você deve ter recebido uma cópia da Licença Pública Geral GNU junto com este
dnl programa;  se  não, escreva para a Free Software Foundation, Inc., 59 Temple

dnl Place, Suite 330, Boston, MA, 02111-1307, USA
dnl
dnl Contatos:
dnl
dnl perry.werneck@gmail.com	(Alexandre Perry de Souza Werneck)
dnl erico.mendonca@gmail.com	(Erico Mascarenhas de Mendonça)
dnl

dnl Process this file with autoconf to produce a configure script.

dnl The minimum version of autoconf required.
AC_PREREQ(2.61)

dnl Initialise automake with the package name, version and
dnl bug-reporting address.
AC_INIT([pw3270-keypads], [5.4], [perry.werneck@gmail.com])

dnl Place auxilliary scripts here.
AC_CONFIG_AUX_DIR([scripts])

dnl Recommended for gtk-doc (https://developer.gnome.org/gtk-doc-manual/stable/settingup_autoconf.html.en)
AC_CONFIG_MACRO_DIR(m4)

dnl Compute the canonical host-system type
AC_CANONICAL_HOST

dnl Initialise automake stuff.
AM_INIT_AUTOMAKE

dnl Checks for programs.
AC_PROG_SED
AC_PROG_LN_S

dnl ---------------------------------------------------------------------------
dnl Check for other programs
dnl ---------------------------------------------------------------------------

AC_PATH_TOOL([ZIP],[zip],[no])
AC_PATH_TOOL([DLLTOOL],[dlltool],[no])
AC_PATH_TOOL([SCOUR], [scour], [no])
AC_PATH_TOOL([APPSTREAMCLI],[appstreamcli], [no])

PKG_CHECK_EXISTS

dnl ---------------------------------------------------------------------------
dnl Set application id & product name
dnl ---------------------------------------------------------------------------

AC_ARG_WITH([product-name], [AS_HELP_STRING([--with-product-name], [Set product name])], [ app_cv_product="$withval" ],[ app_cv_product=`pkg-config --variable=product_name lib3270` ])
AC_DEFINE_UNQUOTED(PRODUCT_NAME, $app_cv_product)
AC_SUBST(PRODUCT_NAME,$app_cv_product)

dnl ---------------------------------------------------------------------------
dnl Directory config
dnl ---------------------------------------------------------------------------

AC_ARG_WITH([build-dir], [AS_HELP_STRING([--with-build-dir], [Setup build path])], [ app_cv_buildir="$withval" ],[ app_cv_buildir="$ac_pwd" ])
AC_SUBST(BASEDIR,$app_cv_buildir)

dnl ---------------------------------------------------------------------------
dnl Configure which files to generate.
dnl ---------------------------------------------------------------------------

AC_CONFIG_FILES(Makefile)
AC_CONFIG_FILES(metainfo.xml)

dnl ---------------------------------------------------------------------------
dnl Output the generated config.status script.
dnl ---------------------------------------------------------------------------
AC_OUTPUT


