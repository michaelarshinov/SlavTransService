# SlavTransService
15 11 2023
* 1 Для более прозрачного процесса тестирования на выход из рамок количества строк метод public void addRecord может
  ** 1.1 возвращать путь файла, в котором произошло добавление строк
* 2 В целях облегчения процесса тестирования DEFAULT_FILE_NAME
  ** 2.1 в классе модификатор доступа константы DEFAULT_FILE_NAME можно изменить чтобы был виден в пакете тестирования
* 3 newFileName = "audit_" + newFileIndex + ".csv"; - тоже лучше открыть доступ к префиксу извне через реализацию метода
    String getReportFileName(int maxLinesPerFile, String directoryPath)
* 4 Разбить метод addRecord на более мелкие, реализовать List<Path> filePaths(directoryPath) - перенести туда логику протестировать его, затем сделать его protected
* 5 String newRecord = userName + ";" + localDate + "\n"; добавить метод формирования строки, которую нужно дописать в файл, чтобы был с чем сравнивать в assert equals
