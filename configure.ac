
dnl----------------------------------------------------------------
dnl
dnl   Package Configurations.
dnl   パッケージ設定。
dnl

dnl
dnl   要求する autoconf のバージョンを指定する。
dnl

AC_PREREQ([2.68])

dnl
dnl   パッケージの情報を指定する。
dnl

AC_INIT(
    [SampleCore],
    [0.0.0],
    [BUG-REPORT-ADDRESS],
    [SampleCore])

dnl
dnl   ツールの出力ディレクトリを指定する。
dnl

AC_CONFIG_AUX_DIR([.Config])

dnl
dnl   適当なバージョンの automake を設定
dnl

AM_INIT_AUTOMAKE(
    [serial-tests]
)

dnl----------------------------------------------------------------
dnl
dnl   プロジェクトの基本設定。
dnl

AC_CONFIG_SRCDIR([Makefile.am])
AC_LANG_CPLUSPLUS

dnl
dnl   デフォルトのコンパイルオプション
dnl

myac_build_type=${AUTOMAKE_BUILD_TYPE:-'Debug'}

myac_cxx_warning_flags='-Wall -Weffc++'
myac_c_warning_flags='-Wall'

myac_cxxflags_debug='-O0 -g -D_DEBUG'
myac_cflags_debug='-O0 -g -D_DEBUG'

myac_cxxflags_release='-O3 -g -DNDEBUG'
myac_cflags_release='-O3 -g -DNDEBUG'

myac_saved_CXXFLAGS=${CXXFLAGS:-''}
myac_saved_CFLAGS=${CFLAGS:-''}

if test "X${myac_build_type}Y" = "XDebugY" ; then
    myac_cxxflags="${myac_cxxflags_debug}   ${myac_saved_CXXFLAGS}"
    myac_cflags="${myac_cflags_debug}   ${myac_saved_CFLAGS}"
else
    myac_cxxflags="${myac_cxxflags_release} ${myac_saved_CXXFLAGS}"
    myac_cflags="${myac_cflags_release} ${myac_saved_CFLAGS}"
fi

CXXFLAGS="${myac_cxxflags} ${myac_cxx_warning_flags}"
CFLAGS="${myac_cflags} ${myac_c_warning_flags}"

dnl
dnl   Project Name Space.
dnl

SAMPLE_CNF_NAMESPACE=Sample
AC_SUBST(SAMPLE_CNF_NAMESPACE)

dnl----------------------------------------------------------------
dnl
dnl   ディレクトリ名。
dnl

AC_CONFIG_HEADERS(config.h)

dnl----------------------------------------------------------------
dnl
dnl   ビルド環境の検査。
dnl

dnl
dnl   Check Programs.
dnl

AC_PROG_CC
AC_PROG_CXX
AM_PROG_AS
AC_PROG_RANLIB

dnl
dnl   Check Header Files.
dnl

dnl
dnl   Check Libraries.
dnl

dnl
dnl   Check Types.
dnl

dnl
dnl   Check Extra Compiler/Linker Options.
dnl

dnl----------------------------------------------------------------
dnl
dnl   Additional Packages.
dnl   外部パッケージの追加
dnl

dnl----------------------------------------------------------------
dnl
dnl   Linker Scripts.
dnl   リンカスクリプトを生成する。
dnl

dnl----------------------------------------------------------------
dnl
dnl   Outputs.
dnl   出力ファイルを設定する。
dnl

dnl
dnl   Basic Features.
dnl

AC_CONFIG_FILES([
    Makefile
])

dnl
dnl   Test Festures.
dnl

dnl
dnl   指定したファイルを生成する。
dnl

AC_OUTPUT

