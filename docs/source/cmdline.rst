.. _cmdline:

Paver コマンドライン
====================

..
    Paver Command Line
    ==================

..
    Paver does sophisticated command line parsing globally and for each task::

Paver は、それぞれのタスク向けに洗練されたコマンドラインを提供します。

  paver [-q] [-n] [-v] [-f pavement] [-h] [option.name=key] [taskname] [taskoptions] [taskname...]

..
    The command line options are:

コマンドラインオプションは次の通りです。

-q
  .. quiet... don't display much info (info and debug messages are not shown)

  quiet... 情報をあまり表示しない (デバッグ情報は表示されません)

-n
  .. dry run... don't actually run destructive commands

  dry run... 破壊的なコマンドを実際には実行しない

-v
  .. verbose... display debug level output

  verbose... デバッグ情報を表示する

-h
  ..  display the command line options and list of available tasks. Note
      that -h can be provided for any task to display the command line options
      and detailed help for that task.

  コマンドラインオプションと利用できるタスク一覧を表示する、-h は任意のタスク向けにそのタスクの詳細ヘルプとコマンドラインオプションを表示できることを覚えておいてください

-f <pavement>
  .. use a different file than "pavement.py"

  "pavement.py" ではない別のファイルを使う

..
    If you run paver without a task, it will only run the "auto" task, if there
    is one. Otherwise, Paver will do nothing.

タスクを指定せずに paver を実行した場合、"auto" タスクがあれば、それを実行します。そうでない場合 Paver は何もしません。

..
    ``paver help`` is the equivalent of ``paver -h``, and ``paver help taskname``
    is the equivalent of ``paver taskname -h``.

``paver help`` は ``paver -h`` は同じです。また ``paver help taskname`` と ``paver taskname -h`` も同じです。

..
    You can set build options via the command line by providing optionname=value.
    The option names can be in dotted notation, so ``foo.bar.baz=something`` will
    set options['foo']['bar']['baz'] = 'something' in the options. If you need
    to enter a value with multiple words, put quotes around the part with the space.

optionname=value を提供することで、コマンドラインからビルドオプションをセットできます。オプション名はドット表記なので ``foo.bar.baz=something`` と指定すると、options['foo']['bar']['baz'] = 'something' にセットされます。スペースを含む複数の単語でオプションを指定するときはクォート (") で囲んでください。

..
    `Important and useful`: Options are set at the point in which they appear in
    the command line. That means that you can set an option before one task
    and then set it to another value for the next task.

`大事なこと`: オプションは、コマンドラインに現れる位置で渡される対象が変わります。あるタスクの前でオプションをセットしてから、その次のタスクへ別の値をセットできます。
