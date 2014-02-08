app.directive('angulartexteditor', function() {
    return {
        restrict: 'A',
        require: '^ngModel',
        link: function (scope, element, attrs, ngModel) {
            $(function () {
                element.jqte({
                    // On focus show the toolbar
                    focus: function () {
                        scope.$apply(function () {
                            element.parents(".jqte").find(".jqte_toolbar").show();
                            element.parents(".jqte").click(function () { element.parents(".jqte").find(".jqte_toolbar").show(); });
                        });
                    },
                    // On blur hide the toolar
                    blur: function () {
                        scope.$apply(function () {
                            element.parents(".jqte").find(".jqte_toolbar").hide();
                        });
                    },
                    // On change refresh the model with the textarea value
                    change: function () {
                        scope.$apply(function () {
                            ngModel.$setViewValue(element.parents(".jqte").find(".jqte_editor")[0].innerHTML);
                        });
                }
                });
                element.parents(".jqte").find(".jqte_toolbar").hide();
            });

            // On render refresh the text area with the model value 
            ngModel.$render = function () {
                element.parents(".jqte").find(".jqte_editor")[0].innerHTML = ngModel.$viewValue || '';
            };
        }
    }
});
