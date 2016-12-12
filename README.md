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




## index.php call in 1st controller
