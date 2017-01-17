# Integrate AngularJS-with-Codeigniter

## create two controller 1) call codigniter controller, 2) call angularjs page of controller

1) codeigniter controller
<?php


class Welcome extends CI_Controller {

	public function index()
	{
		$this->load->view('clients/header');
                $this->load->view('clients/index');
                $this->load->view('clients/footer');
	}
        
        public function clients() {
                
        }
}



## index.php call in 1st controller
2) AngularjS page of controller

class Templates extends CI_Controller {

	public function index()
	{
		$this->load->view('client/index');
	}
	
	public function view($view)
	{
		$this->load->view('clients/'.$view);
	}

}


## add template controller on route.php
$route['templates/(:any)'] = "templates/view/$1";


## create app folder
1)Create app.js

var app =  angular.module('angularApp',['ngRoute','ngSanitize','ngAnimate','datatables','ui.bootstrap.modal','ui.bootstrap','720kb.tooltips','720kb.datepicker']);

app.config(['$routeProvider',
    function($routeProvider,$sceDelegateProvider) { 
        $routeProvider.
       		when('/', {
                templateUrl: 'templates/dashboard.html', 
                controller: 'dashboardController'               
            })
	    }]);
	    

2) Create Controller using angular js on controller folder
app.controller('dashboardController', function(Page,$scope,$http) {
});


