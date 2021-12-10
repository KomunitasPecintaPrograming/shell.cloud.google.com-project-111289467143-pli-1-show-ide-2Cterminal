# shell.cloud.google.com-project-111289467143-pli-1-show-ide-2Cterminal
NEW google Github
function getBaseSpendingLimit() {
  var budgetOrderIterator = AdsApp.budgetOrders().get();
  while (budgetOrderIterator.hasNext()) {
    var budgetOrder = budgetOrderIterator.next();
    var limitText = "";
    if (budgetOrder.getSpendingLimit() == null) {
      limitText = "unlimited";
    } else if (budgetOrder.getTotalAdjustments() == null) {
      limitText = budgetOrder.getSpendingLimit();
    } else {
      limitText = budgetOrder.getSpendingLimit() -
          budgetOrder.getTotalAdjustments();
    }
    Logger.log("Budget Order [" + budgetOrder.getName() +
        "] base spending limit: " + limitText);
  }
}
